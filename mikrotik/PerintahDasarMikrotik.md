## 📡 2. Perintah CLI MikroTik

### 🔧 Navigasi & Struktur Menu

| Perintah         | Deskripsi                              |
| ---------------- | -------------------------------------- |
| `system`         | Masuk ke konfigurasi sistem.           |
| `interface`      | Mengelola interface jaringan.          |
| `ip address`     | Mengatur IP address.                   |
| `ip route`       | Mengatur tabel routing.                |
| `ip dhcp-client` | Mengaktifkan DHCP client di interface. |
| `ip firewall`    | Mengatur firewall/filter NAT.          |
| `user`           | Mengatur pengguna dan hak akses.       |
| `log`            | Melihat log sistem.                    |

---

### 🌐 Konfigurasi IP & Gateway

```bash
/ip address add address=192.168.1.1/24 interface=ether1
/ip route add gateway=192.168.1.254
```

### 🔐 Pengguna & Keamanan

```bash
/user add name=admin group=full password=admin123
```

### 📡 DHCP Client

```bash
/ip dhcp-client add interface=ether1 disabled=no
```

### 🔥 Firewall (Contoh)

```bash
/ip firewall filter add chain=input action=drop protocol=tcp dst-port=23
```

### 🧪 Monitoring & Diagnostik

| Perintah           | Deskripsi                          |
| ------------------ | ---------------------------------- |
| `ping <ip>`        | Ping ke alamat IP.                 |
| `traceroute <ip>`  | Menelusuri rute paket.             |
| `interface print`  | Menampilkan daftar interface.      |
| `ip address print` | Menampilkan IP yang dikonfigurasi. |
| `ip route print`   | Menampilkan tabel routing.         |
| `log print`        | Menampilkan log sistem.            |

### 💾 Penyimpanan & Reset

| Perintah                                 | Deskripsi                     |
| ---------------------------------------- | ----------------------------- |
| `/system reboot`                         | Me-restart perangkat.         |
| `/system shutdown`                       | Mematikan perangkat.          |
| `/system backup save name=config_backup` | Backup konfigurasi.           |
| `/system reset-configuration`            | Reset ke konfigurasi default. |
