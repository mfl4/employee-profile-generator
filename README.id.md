# employee-profile-generator

Utilitas Python ringan yang menyusun profil karyawan dari data mentah dan
mengekstrak field terstruktur dari sebuah kode karyawan. Program ini membangun
baris profil yang mudah dibaca serta kartu karyawan dari potongan teks dan angka
yang terpisah, lalu mengurai kode karyawan menjadi departemen, tahun, inisial,
dan nomor urut.

## Isi Folder

| Berkas          | Keterangan                                                    |
| --------------- | ------------------------------------------------------------- |
| `main.py`       | Program yang menyusun profil karyawan dan mengurai kode.      |
| `LICENSE`       | Dedikasi domain publik CC0 1.0 Universal.                     |
| `.gitignore`    | Aturan abaikan standar Python untuk version control.          |

## Cara Memulai

1. Pastikan Python 3 telah terpasang.
2. Jalankan program dari dalam folder proyek:

   ```bash
   python main.py
   ```

## Cara Kerja

Skrip ini menyusun informasi karyawan dari potongan teks dan angka yang
terpisah, memformat kartu karyawan, lalu mengambil bagian-bagian dari kode
karyawan menggunakan slicing.

```python
first_name = 'John'
last_name = 'Doe'
full_name = first_name + ' ' + last_name
address = '123 Main Street'
address += ', Apartment 4B'
employee_age = 28
employee_info = full_name + ' is ' + str(employee_age) + ' years old'
print(employee_info)

experience_years = 5
experience_info = 'Experience: ' + str(experience_years) + ' years'
print(experience_info)
position = 'Data Analyst'
salary = 75000
employee_card = f'Employee: {full_name} | Age: {employee_age} | Position: {position} | Salary: ${salary}'
print(employee_card)

employee_code = 'DEV-2026-JD-001'
department = employee_code[0:3]
print(department)
year_code = employee_code[4:8]
print(year_code)
initials = employee_code[9:11]
print(initials)
last_three = employee_code[-3:]
print(last_three)
```

### Teknik yang Digunakan

- **Penggabungan** (`+`): menyatukan string, misalnya `first_name + ' ' + last_name`
  menghasilkan `'John Doe'`.
- **Compound assignment** (`+=`): menambahkan teks ke string yang sudah ada,
  misalnya `address += ', Apartment 4B'`.
- **Konversi tipe** (`str()`): mengubah angka menjadi teks agar bisa digabung
  dengan string, misalnya `str(employee_age)`.
- **f-string** (`f'...'`): menyisipkan variabel langsung ke dalam string
  menggunakan placeholder `{}`, lebih rapi daripada penggabungan manual.
- **Slicing** (`[start:stop]`): mengambil sebagian string berdasarkan indeks.
  Nilai `stop` bersifat eksklusif, dan indeks negatif dihitung dari belakang.

### Format Kode Karyawan

Kode karyawan mengikuti pola `DEPT-TAHUN-INISIAL-URUTAN`. Untuk
`employee_code = 'DEV-2026-JD-001'`:

| Posisi indeks   | Field               | Hasil    |
| --------------- | ------------------- | -------- |
| `[0:3]`         | departemen          | `DEV`    |
| `[4:8]`         | tahun               | `2026`   |
| `[9:11]`        | inisial             | `JD`     |
| `[-3:]`         | nomor urut          | `001`    |

## Output yang Diharapkan

```
John Doe is 28 years old
Experience: 5 years
Employee: John Doe | Age: 28 | Position: Data Analyst | Salary: $75000
DEV
2026
JD
001
```

## Konsep Utama

- Menggabungkan string menggunakan concatenation dan operator `+=`.
- Mengonversi angka menjadi string dengan `str()` sebelum menggabungkannya.
- Memformat teks dengan rapi menggunakan f-string.
- Mengambil sebagian string dengan slicing, termasuk indeks negatif.

## Lisensi

Dirilis di bawah [CC0 1.0](LICENSE), menempatkan karya ini ke dalam domain
publik.
