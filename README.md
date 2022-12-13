Nama : Amanda Puspa Negara

NIM : 312210129

Kelas : TI.22.A1

## DAFTAR ISI <br>
| No | Description | Link |
|-----|------|-----|
|1|Tugas Praktikum 8|[Click Here](#tugas-praktikum-8)|
|2|Praktikum 8|[Click Here](#praktikum-8)|
|3|Diagram Class Praktikum 8|[Click Here](#diagram-class-praktikum-8)|
|3|Flowchart Praktikum 8|[Click Here](#flowchart-praktikum-8)|

## Tugas Praktikum 8
Buat program sederhana dengan mengaplikasikan penggunaan class. Buatlah class untuk menampilkan daftar nilai mahasiswa, dengan ketentuan:

- Method tambah() untuk menambah data
- Method tampilkan() untuk menampilkan data
- Method hapus(nama) untuk menghapus data berdasarkan nama
- Method ubah(nama) untuk mengubah data berdasarkan nama
- Buat diagram class, flowchart dan penjelasan programnya pada README.md.
- Commit dan push repository ke github.

## Praktikum 8

### Rumus :

        class mahasiswa:
            def __init__(self, nim, nama, tugas, uts, uas):
                self.nim = nim
                self.nama = nama
                self.tugas = tugas
                self.uts = uts
                self.uas = uas

            def tambah(self,nim,nama,tugas,uts,uas):
                data.nim.append(nim)
                data.nama.append(nama)
                data.tugas.append(tugas)
                data.uts.append(uts)
                data.uas.append(uas)

            def lihat(self):
                for i in range(len(data.nama)):
                    print("|", i+1, "  |", end="")
                    print('{0:<25}'.format(self.nama[i]), end="")
                    print("|", self.nim[i], end="")
                    print(" |", self.tugas[i], end="")
                    print("    |", self.uts[i], end="")
                    print("  |", self.uas[i], " | ", end="")
                    print(f'{((self.tugas[i]*30/100) + (self.uts[i]*35/100) + (self.uas[i]*35/100)) :.2f}', " |")

            def ubah(self,nim,nama,tugas,uts,uas):
                self.nim[no] = nim
                self.nama[no] = nama
                self.tugas[no] = tugas
                self.uts[no] = uts
                self.uas[no] = uas

            def hapus(self):
                del self.nim[no]
                del self.nama[no]
                del self.tugas[no]
                del self.uts[no]
                del self.uas[no]

        data = mahasiswa([],[],[],[],[])

        while True:
            menu = input("\n[(L)ihat, (T)ambah, (U)bah, (H)apus, (K)eluar]:")
            if menu == "t" or menu == "T":
               print("\nTambah Data")
               data.tambah(
                   input("Masukkan NIM : "),
                   input("Masukkan Nama : "),
                   int(input("Nilai Tugas : ")),
                   int(input("Nilai UTS : ")),
                   int(input("Nilai UAS : "))
                   )
               print("\nData berhasil ditambahkan")

            elif menu == "l" or menu == "L":
                print("\nDaftar Nilai")
                print("==========================================================================")
                print("| No  |          Nama           |    NIM    | TUGAS | UTS | UAS |  AKHIR |")
                print("==========================================================================")
                if len(data.nama) != 0:
                    data.lihat()
                else:
                    print("                         TIDAK ADA DATA                               ")
                print("==========================================================================")

            elif menu == "u" or menu == "U":
                print("\nUbah Data")
                ubah = input("Masukkan Nama : ")
                if ubah in data.nama:
                   no = data.nama.index(ubah)
                   print("Masukkan Data Yang Baru : ")
                   data.ubah(
                       input("NIM : "),
                       input("Nama : "),
                       int(input("Nilai Tugas : ")),
                       int(input("Nilai UTS : ")),
                       int(input("Nilai UAS : "))
                       )
                else:
                    print(ubah, "tidak ada di dalam data")

            elif menu == "h" or menu == "H":
                print("\nHapus Data")
                hapus = input("Masukkan Nama : ")
                if hapus in data.nama:
                    no = data.nama.index(hapus)
                    data.hapus()
                    print("Data", hapus, "Berhasil dihapus")
                else:
                    print(hapus, "tidak ada di dalam data")

            elif menu == "k" or menu == "K":
                print("\nTerimakasih\n")
                break

            else:
                print("\nPerintah yang dimasukkan salah!\n")
                
### Program :

![Screenshot (151)](https://user-images.githubusercontent.com/115678845/207253873-e3406c42-d546-4903-9448-e397593f39ef.png)

![Screenshot (152)](https://user-images.githubusercontent.com/115678845/207253893-f058d8ba-8a55-43c4-8be9-0a1fc2a489ed.png)

![Screenshot (153)](https://user-images.githubusercontent.com/115678845/207253902-f8043bf5-1b19-4ef0-982e-e6097dc7f76f.png)

![Screenshot (154)](https://user-images.githubusercontent.com/115678845/207253910-0d82e45c-748d-4299-895d-3c0c8f504803.png)

### Hasil Run & Penjelasan Program :

- Pertama kita mendeklarasikan sebuah class mahasiswa yang didalamnya terdapat atribut NIM, Nama, nilai tugas, nilai UTS dan nilai UAS. Jangan lupa, untuk mendeklarasikan sebuah class didalam OOP kita harus menggunakan def__init__ dan juga self.

      class mahasiswa:
          def __init__(self, nim, nama, tugas, uts, uas):
              self.nim = nim
              self.nama = nama
              self.tugas = tugas
              self.uts = uts
              self.uas = uas

- Seperti biasa, deklarasikan satu dictionary kosong sebagai tempat menyimpan data-data yang sudah kita input. Ada 5 list kosong yang nantinya berisi NIM, Nama, nilai tugas, nilai UTS dan nilai UAS.

      data = mahasiswa([],[],[],[],[])

- Kita akan buat beberapa method untuk menambahkan, menampilkan, menghapus, mengubah data mahasiswa. Pertama membuat method tambah(), method ini berfungsi untuk menambahkan data. Dalam method ini kita menggunakan append() supaya data yang terakhir ditambahkan ada di urutan list paling akhir.

      def tambah(self,nim,nama,tugas,uts,uas):
              data.nim.append(nim)
              data.nama.append(nama)
              data.tugas.append(tugas)
              data.uts.append(uts)
              data.uas.append(uas)

- Ini tampilan jika kita menginput method : Tambah()

![Screenshot (144)](https://user-images.githubusercontent.com/115678845/207254422-6679ba57-6452-4635-b6ab-2a6118ebab6e.png)
![Screenshot (145)](https://user-images.githubusercontent.com/115678845/207254489-ecb51184-6549-470d-b2e9-ffe9146c6290.png)

Fungsi membuat method lihat() yaitu untuk menampilkan seluruh data yang sudah kita tambahkan tadi. Jika tidak ada data sama sekali, maka akan muncul tulisan TIDAK ADA DATA.

      def lihat(self):
              for i in range(len(data.nama)):
                  print("|", i+1, "  |", end="")
                  print('{0:<25}'.format(self.nama[i]), end="")
                  print("|", self.nim[i], end="")
                  print(" |", self.tugas[i], end="")
                  print("    |", self.uts[i], end="")
                  print("  |", self.uas[i], " | ", end="")
                  print(f'{((self.tugas[i]*30/100) + (self.uts[i]*35/100) + (self.uas[i]*35/100)) :.2f}', " |")

- Ini tampilan jika kita menginput method : Lihat()

![Screenshot (146)](https://user-images.githubusercontent.com/115678845/207254699-0c0c22b6-d431-4985-9db8-b0402bb5c1e3.png)

- Fungsi membuat method ubah() yaitu untuk mengubah data. jika method ini diinput, maka data Nama, NIM, nilai tugas, nilai UTS, nilai UAS index nomor - (no) akan diubah sesuai dengan inputan dari user. Index ke - (no) akan dicari secara otomatis sesuai dengan nama yang ingin diubah oleh user.

      def ubah(self,nim,nama,tugas,uts,uas):
              self.nim[no] = nim
              self.nama[no] = nama
              self.tugas[no] = tugas
              self.uts[no] = uts
              self.uas[no] = uas
              
- Ini tampilan jika kita menginput method : Ubah()

![Screenshot (147)](https://user-images.githubusercontent.com/115678845/207254921-99b6ba2b-7112-4d1a-95e3-e1c5dc9f4e47.png)

![Screenshot (148)](https://user-images.githubusercontent.com/115678845/207254950-e32e8c10-c0d2-4a10-ba70-ccad436ffdc1.png)

![Screenshot (149)](https://user-images.githubusercontent.com/115678845/207255005-00643ffc-5013-497c-b957-45f41bdac657.png)

- Terakhir kita membuat method hapus(), yang berfungsi untuk menghapus data berdasarkan nama. Kita bisa menggunakan del untuk menghapus datanya. Seperti sebelumnya, nomor index list yang akan dihapus disesuaikan dengan inputan dari user. Yaitu index nomor ke - (no).

      def hapus(self):
              del self.nim[no]
              del self.nama[no]
              del self.tugas[no]
              del self.uts[no]
              del self.uas[no]
              
- Ini tampilan jika kita menginput method : Hapus()

![Screenshot (155)](https://user-images.githubusercontent.com/115678845/207255217-4dde19e0-d256-4882-a5ea-81e409aa9a8f.png)

### Diagram Class Praktikum 8

![Flowcht8](https://user-images.githubusercontent.com/115678845/207255310-482792f3-f5fa-4fb3-bf83-40b4fb00292d.jpg)

Flowchart Praktikum 8

![Flowchart_8](https://user-images.githubusercontent.com/115678845/207255386-738ad693-b015-45a0-9ec2-d81642cdee28.png)

## Sekian, Terima kasih
