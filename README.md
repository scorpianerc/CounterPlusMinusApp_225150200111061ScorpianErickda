# Counter Plus-Minus App

## Deskripsi Aplikasi
Aplikasi counter menggunakan **Jetpack Compose** dengan dua tombol: Tambah (+) dan Kurang (-).

## Penjelasan Kode

### MainActivity.kt

#### Implementasi State Management
```kotlin
//State Declaration
var count by remember { mutableStateOf(0) }
```
1. mutableStateOf(0): Membuat state yang dapat berubah dengan nilai awal 0
2. remember: Menyimpan state dan mencegah reset saat recomposition
3. by: Memungkinkan akses langsung ke nilai tanpa .value

```kotlin
//State Update Pattern
Row(
            horizontalArrangement = Arrangement.spacedBy(16.dp)
        ) {
            // Tombol Kurang (-)
            Button(onClick = {
                // Tidak Boleh Kurang dari 0
                if (count > 0) {
                    count--
                }
            }) {
                Text("Kurang")
            }
            // Tombol Tambah (+)
            Button(onClick = { count++ }) {
                Text("Tambah")
            }
        }
```
1. Row memungkinkan komponen secara horizontal dan memiliki jarak 16 dp secara horizontal
2. Terdapat tombol dengan label "kurang". Pada tombol ini jika diklik nilainya akan berkurang 1 namun tidak akan menyentuh nilai dibawah 0
3. Terdapat tombol dengan label "tambah". Saat ditekan nilainya akan bertambah 1

## Mengapa Compose Lebih Sederhana daripada XML?
Jetpack compose lebih sederhana dibanding dengan XML karena .... 
1. Compose memakai paradigma deklaratif dan satu bahasa yaitu Kotlin, sedangkan XML masih bersifat imperatif dan kodenya terpisah (UI di XML, logic di Kotlin/Java).
2. UI ditulis dalam bentuk fungsi dan bisa dipecah menjadi composable kecil-kecil yang mudah dipakai ulang.
3. Tidak memerlukan nested XML panjang, sehingga tampak clean dan modular.
