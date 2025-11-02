# Tugas P7 Praktikum 3
# labpy03
Program ini ditulis menggunakan bahasa Python dan bertujuan untuk menampilkan sejumlah bilangan acak (random) yang lebih kecil dari 0.5.
Program akan meminta pengguna untuk memasukkan sebuah nilai integer N, lalu akan menghasilkan N bilangan acak di bawah 0.5, sekaligus menampilkannya di layar.
1. Import modul random
   from random import random
   Baris ini mengimpor fungsi random() dari modul bawaan Python random.
Fungsi random() menghasilkan bilangan acak floating point antara 0.0 dan 1.0.
3. input dari pengguna
   n = int(input("Masukkan nilai N: "))
   Pengguna diminta untuk memasukkan sebuah angka bulat N, yaitu jumlah bilangan acak yang ingin ditampilkan.
4. inisialisasi variabel penghitung
   count = 0
   Variabel count digunakan untuk menghitung berapa banyak bilangan acak yang sudah ditampilkan.
5. perulangan untuk menghasilkan bilangan acak
   while count < n:
    angka = random()
    if angka < 0.5:
        count += 1
        print(f"data ke: {count} => {angka}")
   Perulangan while berjalan selama jumlah bilangan yang dicetak (count) masih kurang dari N.
Pada setiap iterasi, program menghasilkan angka acak (angka = random()).
Jika angka tersebut kurang dari 0.5, maka angka itu akan ditampilkan ke layar dan penghitung count ditambah 1.
Dengan demikian, program hanya menghitung dan menampilkan angka yang < 0.5, dan mengabaikan yang lainnya.
6. pesan akhir
   print("Selesai")
Setelah count mencapai N, perulangan berhenti dan program menampilkan pesan penutup "Selesai".

# MEMBUAT MODAL LABA PERULANGAN
1. Inisialisasi modal awal
   modal_awal = 100_000_000
Modal awal ditetapkan sebesar Rp 100.000.000.
2. Inisialisasi variabel total laba
   total_laba = 0
   Variabel total_laba digunakan untuk menampung akumulasi laba dari bulan 1 hingga 8.
3. Perulangan untuk Tiap Bulan
   for bulan in range(1, 9):
   Program melakukan perulangan dari bulan ke-1 hingga bulan ke-8.
4. Menentukan Persentase Laba per Bulan
   if bulan <= 2:
    laba_persen = 0  # Bulan 1-2: tidak ada laba
   elif bulan <= 4:
    laba_persen = 1  # Bulan 3-4: laba 1%
   elif bulan <= 7:
    laba_persen = 5  # Bulan 5-7: laba 5%
   else:
    laba_persen = 2  # Bulan 8: laba 2%
   Setiap rentang bulan memiliki persentase laba yang berbeda:
   Bulan 1–2: tidak ada laba (0%)
   Bulan 3–4: 1%
   Bulan 5–7: 5%
   Bulan 8: 2% (turun 3% dari 5%)
5. Menghitung Laba Bulan Tersebut
   laba_bulan_ini = modal_awal * (laba_persen / 100)
   total_laba += laba_bulan_ini
   Laba dihitung berdasarkan persentase bulan itu, lalu ditambahkan ke total_laba.
6. Menampilkan Informasi per Bulan
   print(f"Bulan ke-{bulan} laba {laba_persen}% = Rp {laba_bulan_ini:,.0f}")
7. Menampilkan Total Laba Setelah 8 Bulan
   print(f"\nTotal laba selama 8 bulan = Rp {total_laba:,.0f}")

# MEMBUAT ATM VISUAL DALAM BENTUK CODING
1. Inisialisasi saldo
   saldo = 1000000
   Variabel saldo menyimpan jumlah uang awal (dalam satuan rupiah) yang tersedia di "rekening" pengguna.
2. Loop utama
   while saldo > 0:
    ...
   Program masuk ke loop while yang berjalan selama saldo lebih besar dari 0.
   Pada setiap iterasi, program menampilkan informasi dan menu.
3. Menampilkan saldo dan menu
   print(f"Saldo saat ini: Rp {saldo}")
   print("1. Tarik Uang")
   print("2. Keluar")
   pilihan = int(input("Pilih menu (1/2): "))
   Menampilkan saldo saat ini dan dua pilihan: tarik uang atau keluar.
   input() menerima pilihan dari pengguna dan int() mengubahnya menjadi bilangan bulat.
4. Pilihan tarik uang (1)
   if pilihan == 1:
   jumlah = int(input("Masukkan jumlah penarikan: "))
   if jumlah <= saldo:
        saldo -= jumlah
        print("Penarikan berhasil!")
   else:
        print("Saldo tidak cukup!")
   Program meminta jumlah penarikan.
   Jika jumlah kurang dari atau sama dengan saldo, maka saldo dikurangi dan penarikan dinyatakan berhasil.
   Jika jumlah lebih besar dari saldo, program menolak penarikan.
   Perhatian: Tidak ada pengecekan apakah jumlah negatif atau nol; tidak ada pembatasan denom (mis. harus kelipatan 50000).
5. Pilihan keluar (2)
   elif pilihan == 2:
    print("Terima kasih telah menggunakan ATM!")
    break
   Program menampilkan pesan terima kasih dan keluar dari loop (mengakhiri program).
