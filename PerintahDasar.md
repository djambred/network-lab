# 📘 Daftar Perintah Dasar & Tambahan CLI Router (Cisco-style)

## 🔧 Perintah Dasar

| Perintah                                        | Deskripsi                                                                           |
| ----------------------------------------------- | ----------------------------------------------------------------------------------- |
| `enable`                                        | Memasuki mode **privileged EXEC** (akses penuh).                                    |
| `configure terminal` / `conf t`                 | Memasuki mode **konfigurasi global**.                                               |
| `interface <interface_type> <interface_number>` | Masuk ke mode konfigurasi antarmuka (misal: `interface eth1`).                      |
| `ip address <ip_address> <subnet_mask>`         | Mengatur alamat IP untuk antarmuka tertentu.                                        |
| `no shutdown`                                   | Mengaktifkan antarmuka (secara default, antarmuka biasanya dalam keadaan shutdown). |
| `exit`                                          | Keluar dari mode konfigurasi saat ini.                                              |
| `logout`                                        | Keluar dari sesi CLI.                                                               |
| `hostname <nama_host>`                          | Mengganti nama host perangkat.                                                      |
| `banner motd <pesan>`                           | Menampilkan pesan saat login (Message of the Day).                                  |
| `enable secret <password>`                      | Mengatur password untuk masuk ke mode privileged EXEC.                              |
| `?`                                             | Menampilkan bantuan atau daftar perintah yang tersedia pada level saat ini.         |

---

## 🧩 Perintah Konfigurasi dan Penyimpanan

| Perintah                             | Deskripsi                                                 |
| ------------------------------------ | --------------------------------------------------------- |
| `show running-config`                | Menampilkan konfigurasi aktif saat ini (RAM).             |
| `show startup-config`                | Menampilkan konfigurasi yang disimpan (NVRAM).            |
| `copy running-config startup-config` | Menyimpan konfigurasi aktif ke startup-config (permanen). |
| `erase startup-config`               | Menghapus konfigurasi startup untuk reset perangkat.      |
| `reload`                             | Merestart perangkat.                                      |

---

## 🛠️ Perintah Monitoring dan Troubleshooting

| Perintah                  | Deskripsi                                                  |
| ------------------------- | ---------------------------------------------------------- |
| `show version`            | Menampilkan informasi versi perangkat & uptime.            |
| `show interfaces`         | Menampilkan status & statistik semua antarmuka.            |
| `show ip interface brief` | Ringkasan semua antarmuka dengan status IP & konektivitas. |
| `show ip route`           | Menampilkan tabel routing yang digunakan perangkat.        |
| `ping <ip_address>`       | Menguji konektivitas ke alamat IP tertentu.                |
| `traceroute <ip_address>` | Melacak jalur paket ke alamat IP.                          |

---

## 💡 Catatan

- Gunakan perintah `write` atau `copy run start` untuk menyimpan konfigurasi agar tetap ada setelah reboot.
- CLI berbasis FRRouting, Cisco, atau MikroTik akan memiliki gaya yang mirip, tetapi detail sintaksis bisa berbeda.

---
