### Sistem Pengurusan Perpustakaan
- Senario
Sebuah perpustakaan kolej masih menggunakan kaedah manual untuk merekod
pinjaman dan pemulangan buku. Pengurus bercadang membangunkan sistem
berkomputer bagi meningkatkan kecekapan operasi.


### kenalpasti
1. aktor sistem
	- Pelanggan (pelajar)
		- Mencari buku, menyemak ketersediaan naskah, membuat tempahan, memperbaharui tempoh pinjaman, dan menyemak rekod denda
		- Pustakawan (staf perpustakaan)
			- Mengurus pendaftaran pengguna, merekod transaksi pinjaman dan pemulangan, mengemas kini katalog bahan bacaan, menjana laporan, dan mengurus denda
		- pentadbir sistem
			- Menyelenggara pelayan, mengurus pangkalan data, menetapkan kebenaran akses (privilege) pengguna, dan memastikan keselamatan sistem berjalan lancar
2. input, proses dan output sistem
	- input:
		- pendaftaran penggua
		- katalog bahan
		- transaksi
	- proses:
		- **sirkulasi:** Sistem mengira tarikh jangka pemulangan dan menjana denda jika peminjam lewat
		- **Carian & Semakan:** Pemadanan carian kata kunci atau pengarang oleh pengguna dengan senarai inventori yang ada
		- **Kemaskini Data:** Menukar status buku daripada 'Tersedia' kepada 'Dipinjam', atau mengemas kini rekod ahli
	- ouput:
		- **Resit Transaksi:** Maklumat tarikh pinjaman dan tarikh pemulangan
		- **Laporan & Statistik:** Analisis data penggunaan perpustakaan (jumlah buku dipinjam, senarai buku paling popular, denda terkumpul)
		- **Makluman/Notifikasi:** E-mel peringatan secara automatik untuk memulangkan buku atau notis bahan yang telah ditempah (_reservation_) sedia untuk diambil
### cadangkan satu sistem maklumat yang sesuai
- ##### komponen modul sistem
	- **Modul Katalog (OPAC):** Membolehkan pengguna mencari buku, jurnal, atau bahan digital secara dalam talian menggunakan tajuk, pengarang, atau kata kunci
	- **Modul Peredaran:** Mengendalikan proses daftar masuk dan daftar keluar (peminjaman) buku, pengiraan denda, dan pembaharuan tempoh pinjaman secara automatik
	- **Modul Perolehan:** Menguruskan pembelian, penerimaan, dan rekod invois bahan baharu bersama pembekal
	- **Modul Pengguna:** Mengurus pendaftaran, profil, dan semakan rekod sejarah pinjaman ahli perpustakaan
- ##### cadangan teknologi perisian
	- **Sistem Sumber Terbuka (Open Source):** Penggunaan sistem seperti **Koha** adalah sangat disyorkan. Ia adalah sistem gred profesional, berskala besar, dan digunakan oleh pelbagai institusi
	- **Pangkalan Data (Database):** MySQL atau PostgreSQL untuk menyimpan data rekod inventori buku, transaksi, dan maklumat pengguna yang selamat
	- **Platform Pelayan:** Pengehosan berasaskan awan (_cloud-based_) untuk membolehkan akses 24/7 dari mana-mana lokasi melalui pelayar web