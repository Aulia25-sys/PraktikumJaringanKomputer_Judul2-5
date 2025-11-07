Topologi Jaringan Sebelum dilakukan konfigurasi:

<img width="431" height="214" alt="image" src="https://github.com/user-attachments/assets/788b0c7d-5058-428c-b6c7-90de6123c4e1" />

Berdasarkan pada gambar dapat dilihat bahwa warna merah pada kabel menunjukkan link belum aktif karena interface router belum dikonfigurasi atau belum diaktifkan (shutdown state). Router masih belum memiliki IP address atau perintah no shutdown, jadi koneksi belum siap. Sementara kabel dari switch ke PC-A berwarna hijau karena port di switch dan PC otomatis aktif secara default, port switch 2960 langsung hidup (auto up) saat mendeteksi perangkat aktif di ujungnya karena masih dalam satu jaringan serta switch hanya bisa membaca satu jaringan tidak seperti router.

---

Ping dari PC-A ke PC-B sebelum konfigurasi

<img width="519" height="301" alt="image" src="https://github.com/user-attachments/assets/4da379ce-3939-45fb-8a16-01181df22f20" />

Dapat dilihat dari gambar ini  bahwa ping gagal karena belum ada konfigurasi IP pada router. Router berfungsi sebagai penghubung antar jaringan (gateway). PC-A (192.168.1.x) dan PC-B (192.168.0.x) berada di subnet berbeda, jadi mereka tidak bisa saling berkomunikasi tanpa router. Saat router belum dikonfigurasi, tidak ada routing antar-subnet, sehingga paket ICMP dari PC-A tidak menemukan jalur ke PC-B.


Ping dari PC-A ke PC-B setelah di konfigurasi

<img width="448" height="205" alt="image" src="https://github.com/user-attachments/assets/b99ba2d8-a055-44ae-bd03-2a13fecf2220" />

Setelah router dikonfigurasi dengan IP address di kedua interface (192.168.1.1 dan 192.168.0.1) dan perintah ipv6 unicast-routing serta no shutdown dijalankan, router mulai berfungsi sebagai penghubung antar-jaringan. Paket dari PC-A menuju router, diteruskan ke subnet PC-B. Karena semua alamat IP dan gateway sudah benar, maka routing antar dua jaringan berlangsung sukses, sehingga ping berhasil.

---

Ping dari PC-B ke PC-A sebelum di konfigurasi

<img width="514" height="303" alt="image" src="https://github.com/user-attachments/assets/b3a727dc-7e52-418b-82f9-1c5d5086a67c" />

Sama seperti sebelumnya, pada tahap awal router belum dikonfigurasi. Jadi PC-B pun tidak bisa mengirim paket ICMP ke PC-A karena gateway (router) belum aktif atau belum memiliki IP.
Walaupun PC-B sudah terhubung secara fisik ke router, tidak ada rute logis untuk mencapai subnet 192.168.1.x, sehingga ping-nya timeout.

<img width="453" height="204" alt="image" src="https://github.com/user-attachments/assets/ba314674-024e-441b-9f0d-b6d1559ae0f8" />

Setelah konfigurasi router selesai dan kedua interface aktif (up/up), routing dua arah sudah berjalan. Router sekarang memiliki informasi lengkap tentang kedua jaringan dan dapat meneruskan paket dari PC-B ke PC-A maupun sebaliknya.
Port switch dan PC juga sudah aktif (lampu hijau), sehingga jalur komunikasi penuh terbentuk dan ping sukses.

---

Link Youtube: https://youtu.be/GgW-JaHoR-A





