# Materi Jaringan Komputer  
## Routing Statis 
### oleh Jefry Sunupurwa Asri S.Kom, M.Kom
---

## 🎯 Tujuan Pembelajaran

Setelah mempelajari materi ini, mahasiswa mampu:
- Menjelaskan konsep dan karakteristik routing statis.
- Mengkonfigurasi routing statis pada perangkat Cisco dan MikroTik.
- Menggunakan Containerlab untuk membangun topologi jaringan virtual.
- Menguji konektivitas antar jaringan menggunakan perintah ping dan traceroute.

---

## 📚 Daftar Isi

1. [Pendahuluan Routing Statis](#1-pendahuluan-routing-statis)  
   - Konsep Dasar  
   - Kelebihan dan Kekurangan  
   - Tabel Routing  
2. [Konfigurasi Routing Statis pada Cisco IOS](#2-konfigurasi-routing-statis-pada-cisco-ios)  
   - Sintaks Perintah Dasar  
   - Contoh Konfigurasi  
   - Verifikasi  
3. [Konfigurasi Routing Statis pada MikroTik RouterOS](#3-konfigurasi-routing-statis-pada-mikrotik-routeros)  
   - Sintaks CLI dan WinBox  
   - Contoh Konfigurasi  
   - Verifikasi  
4. [Laboratorium Virtual dengan Container](#4-laboratorium-virtual-dengan-container)  
   - Pengenalan Containerlab  
   - Instalasi dan Persiapan  
   - Studi Kasus: Cisco + MikroTik  
     - Topologi  
     - Langkah-langkah Konfigurasi  
     - Pengujian Konektivitas  
5. [Troubleshooting Umum](#5-troubleshooting-umum)

---

## 1. Pendahuluan Routing Statis

### Konsep Dasar

Routing statis adalah proses konfigurasi path atau jalur secara manual pada sebuah router untuk meneruskan paket data ke jaringan tujuan. Administrator jaringan secara eksplisit mendefinisikan rute ke setiap jaringan yang tidak terhubung langsung (*non-directly connected*). Jalur ini bersifat tetap dan tidak berubah kecuali diubah secara manual.

---

### Kelebihan dan Kekurangan

| Kelebihan                              | Kekurangan                                                                            |
|----------------------------------------|----------------------------------------------------------------------------------------|
| Beban CPU rendah                       | Tidak skalabel — harus dikonfigurasi manual di setiap router                         |
| Keamanan lebih tinggi                  | Rentan kesalahan konfigurasi (IP/gateway)                                             |
| Kontrol penuh oleh administrator       | Tidak adaptif terhadap perubahan topologi                                             |

---

### Tabel Routing

Setiap router memiliki tabel routing yang berisi:
- **Destination Network**: Alamat jaringan tujuan.
- **Subnet Mask**: Subnet mask dari tujuan.
- **Next-Hop Address**: IP router selanjutnya.
- **Outgoing Interface**: Interface untuk mengirim paket ke tujuan.

---

## 2. Konfigurasi Routing Statis pada Cisco IOS

### Sintaks Perintah Dasar

```bash
Router(config)# ip route <destination-network> <subnet-mask> <next-hop-address | outgoing-interface>
```
Contoh:
```bash
RouterA(config)# ip route 10.10.10.0 255.255.255.0 192.168.1.2
```

Verifikasi
```bash
RouterA# show ip route
```

## 3. Konfigurasi Routing Statis pada MikroTik RouterOS

### Sintaks CLI
```bash
/ip route add dst-address=10.10.10.0/24 gateway=192.168.1.2
```
### WinBox
```bash
IP → Routes → (+)
Dst Address: 10.10.10.0/24
Gateway: 192.168.1.2
```
### Verifikasi
CLI:
```bash
/ip route print
```
WinBox:
```bash
IP → Routes
```

## 4. Laboratorium Virtual dengan Container
Pengenalan Containerlab
Containerlab adalah CLI tool ringan untuk membuat laboratorium jaringan virtual menggunakan Docker container. Mendukung node Cisco, MikroTik, FRRouting, dan lainnya.
<br>
detail ada di modul praktikum Readme.md

## 5. Troubleshooting Umum

| Masalah                         | Solusi                                                                 |
|---------------------------------|------------------------------------------------------------------------|
| ❌ PC1 tidak bisa ping PC2      | Cek IP, gateway, routing table, gunakan `tcpdump`                     |
| ❌ Ping dari Cisco gagal        | Gunakan `show ip interface brief`, pastikan interface aktif           |
| ❌ Routing MikroTik tidak aktif | Gunakan `/ip route print`                                             |
| ❌ Tidak bisa deploy lab        | Cek syntax YAML dan image tersedia di local Docker                    |


