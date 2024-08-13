
### Contoh Kode Kotlin dan Penjelasan:

```kotlin
import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)  // Menghubungkan activity dengan layout XML

        // Menghubungkan elemen UI dari XML ke variabel Kotlin
        val textViewTitle: TextView = findViewById(R.id.textViewTitle)
        val editTextName: EditText = findViewById(R.id.editTextName)
        val buttonSubmit: Button = findViewById(R.id.buttonSubmit)

        // Menangani aksi klik pada tombol Submit
        buttonSubmit.setOnClickListener {
            val name = editTextName.text.toString()  // Mengambil teks dari EditText
            textViewTitle.text = "Hello, $name!"     // Mengubah teks pada TextView
        }
    }
}
```

### Penjelasan Atribut XML dalam Kotlin:

- **`findViewById<T>(R.id.element_id)`**:
  - Menggunakan `findViewById` untuk menghubungkan elemen UI dari XML ke variabel Kotlin.
  - `<T>` adalah tipe elemen UI, seperti `TextView`, `EditText`, atau `Button`.

- **`setOnClickListener { ... }`**:
  - Mengatur aksi yang akan dilakukan ketika elemen (misalnya, tombol) diklik.
  - Pada contoh di atas, aksi yang dilakukan adalah mengubah teks `TextView` sesuai dengan input dari `EditText`.

### Penjelasan Atribut XML dalam Kotlin:

1. **`android:id`**:
   - ID unik yang digunakan untuk merujuk elemen UI dalam kode Kotlin. Misalnya, `R.id.textViewTitle` digunakan untuk menghubungkan `TextView` dengan variabel `textViewTitle`.

2. **`android:layout_width` dan `android:layout_height`**:
   - Mengatur lebar (`layout_width`) dan tinggi (`layout_height`) elemen UI. Dalam Kotlin, ukuran ini bisa berupa `wrap_content`, `match_parent`, atau nilai tetap dalam `dp`.

3. **`android:text`**:
   - Menentukan teks yang akan ditampilkan pada elemen seperti `TextView` atau `Button`. Dalam Kotlin, teks ini bisa diubah menggunakan `textViewTitle.text = "New Text"`.

4. **`android:textSize`**:
   - Mengatur ukuran teks dalam `sp` (scale-independent pixels). Dalam Kotlin, ukuran teks bisa diatur menggunakan `textViewTitle.textSize = 24f`.

5. **`android:textColor`**:
   - Menentukan warna teks menggunakan kode warna hexadecimal. Dalam Kotlin, warna teks bisa diubah menggunakan `textViewTitle.setTextColor(Color.parseColor("#000000"))`.

6. **`android:hint`**:
   - Teks petunjuk yang ditampilkan pada elemen input seperti `EditText`. Dalam Kotlin, hint ini bisa diatur menggunakan `editTextName.hint = "Enter your name"`.

7. **`android:inputType`**:
   - Menentukan jenis input yang diizinkan dalam elemen seperti `EditText`, seperti teks, angka, email, dll. Dalam Kotlin, tipe input bisa diatur menggunakan `editTextName.inputType = InputType.TYPE_CLASS_TEXT`.

8. **`android:gravity`**:
   - Mengatur posisi konten di dalam elemen UI, seperti `TextView`. Dalam Kotlin, gravitasi ini bisa diatur menggunakan `textViewTitle.gravity = Gravity.CENTER`.

9. **`android:layout_gravity`**:
   - Mengatur posisi elemen UI dalam induknya, seperti menempatkan `Button` di tengah induknya. Dalam Kotlin, ini bisa diatur menggunakan `buttonSubmit.layoutParams = (buttonSubmit.layoutParams as LinearLayout.LayoutParams).apply { gravity = Gravity.CENTER }`.

10. **`android:padding` dan `android:layout_margin`**:
    - `padding` menambahkan ruang di dalam batas elemen, sementara `margin` menambahkan ruang di luar batas elemen. Dalam Kotlin, ini bisa diatur menggunakan `view.setPadding(16, 16, 16, 16)` atau `layoutParams.setMargins(16, 16, 16, 16)`.
