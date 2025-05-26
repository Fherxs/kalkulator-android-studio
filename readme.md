Main Activity 

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private EditText editText1, editText2;
    private Button calculateButton;
    private TextView resultTextView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Inisialisasi Views
        editText1 = findViewById(R.id.editTextText);
        editText2 = findViewById(R.id.editTextText3);
        calculateButton = findViewById(R.id.button);
        resultTextView = findViewById(R.id.textViewResult);

        calculateButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Mengambil nilai dari EditText
                String input1 = editText1.getText().toString().toLowerCase();
                String input2 = editText2.getText().toString().toLowerCase();

                // Validasi input
                if (input1.isEmpty() || input2.isEmpty()) {
                    resultTextView.setText("Data tidak valid. Silakan isi kedua input.");
                } else {
                    try {
                        // Mengonversi input pertama dan kedua
                        int num1 = convertInputToNumber(input1);
                        int num2 = convertInputToNumber(input2);

                        // Mengecek jika salah satu input adalah angka, dan yang lainnya adalah kata
                        if (num1 == -1 && num2 != -1) {
                            // Jika input pertama adalah kata dan input kedua adalah angka
                            num1 = convertTextToNumber(input1);
                        } else if (num2 == -1 && num1 != -1) {
                            // Jika input kedua adalah kata dan input pertama adalah angka
                            num2 = convertTextToNumber(input2);
                        }

                        // Mengecek apakah kedua input valid setelah konversi
                        if (num1 == -1 || num2 == -1) {
                            resultTextView.setText("Input harus berupa angka valid atau kata (satu, dua, tiga, ...).");
                        } else {
                            // Melakukan operasi penjumlahan
                            int result = num1 + num2;

                            // Menampilkan hasil ke TextView
                            resultTextView.setText("Hasil: " + result);
                        }

                    } catch (Exception e) {
                        resultTextView.setText("Terjadi kesalahan.");
                    }
                }
            }
        });
    }

    // Fungsi untuk mengonversi input ke angka
    private int convertInputToNumber(String input) {
        try {
            return Integer.parseInt(input); // Coba konversi ke integer
        } catch (NumberFormatException e) {
            return -1; // Menandakan bahwa input bukan angka
        }
    }

    // Fungsi untuk mengonversi kata-kata ke angka dengan if-else
    private int convertTextToNumber(String text) {
        if (text.equals("satu")) {
            return 1;
        } else if (text.equals("dua")) {
            return 2;
        } else if (text.equals("tiga")) {
            return 3;
        } else if (text.equals("empat")) {
            return 4;
        } else if (text.equals("lima")) {
            return 5;
        } else if (text.equals("enam")) {
            return 6;
        } else if (text.equals("tujuh")) {
            return 7;
        } else if (text.equals("delapan")) {
            return 8;
        } else if (text.equals("sembilan")) {
            return 9;
        } else if (text.equals("sepuluh")) {
            return 10;
        } else {
            return -1; // Menandakan input tidak valid
        }
    }
}

