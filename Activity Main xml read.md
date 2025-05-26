<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp"
    android:gravity="center">

    <!-- Input untuk Angka Pertama -->
    <EditText
        android:id="@+id/editTextText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Masukkan angka pertama (angka atau kata)"
        android:inputType="text" />

    <!-- Input untuk Angka Kedua -->
    <EditText
        android:id="@+id/editTextText3"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Masukkan angka kedua (angka atau kata)"
        android:inputType="text" />

    <!-- Tombol untuk Melakukan Perhitungan -->
    <Button
        android:id="@+id/button"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Hitung"
        android:layout_marginTop="16dp" />

    <!-- TextView untuk Menampilkan Hasil atau Pesan Kesalahan -->
    <TextView
        android:id="@+id/textViewResult"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Hasil: "
        android:textSize="18sp"
        android:layout_marginTop="16dp"
        android:gravity="center" />

</LinearLayout>
