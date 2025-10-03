# ✅ Langkah Lengkap Installasi WSL via PowerShell (Run as Administrator)
1. Buka PowerShell sebagai Administrator
Klik Start → cari "PowerShell" → klik kanan → Run as Administrator
2. Aktifkan Fitur Pendukung WSL Secara Manual (Opsional tapi Disarankan)
```bash
wsl --install
```
_Gunakan ini jika gagal_
```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
3. Restart Komputer
---

# ✅ Setelah Restart via PowerShell (Run as Administrator)
Buka PowerShell sebagai Administrator Klik Start → cari "PowerShell" → klik kanan → Run as Administrator
1. Install WSL dan Distro (Ubuntu)
```powershell
wsl --install -d Ubuntu
```
2. Set WSL 2 sebagai Default Secara Manual
```powershell
wsl --set-default-version 2
```
3. Update Kernel WSL
```powershell
wsl --update
```
4. Install Windows Terminal (bisa juga install via microsoft store)
```powershell
winget install --id Microsoft.WindowsTerminal -e
```
5. Jalankan Ubuntu dan Buat User Linux
Setelah install:

        Jalankan "Ubuntu" dari Start Menu Terminal.
        Buat username dan password Linux.
        Siap digunakan.


# ✅ Setup WSL Ubuntu via Terminal (Run as Administrator)
1. Set User to to Root
```bash
nano /etc/wsl.conf
```
_isikan seperti dibawah ini_
```bash
[boot]
systemd=true

[user]
default=root
```
<b>untuk exit ctrl+x dan y dan enter</b><br><br>

2. Update APT dan install tools:
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y build-essential curl git unzip zip
```

3. Install ZSH
```bash
apt install zsh -y
```
4. Install Oh-My-Zsh
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

5. Install Powerline Font (MesloLGS NF)
Untuk tampilan tema yang bagus seperti powerlevel10k, kamu harus install font ini di Windows:

💾 Unduh font:
👉 https://github.com/romkatv/powerlevel10k#manual-font-installation

        Unduh dan install semua ini:

        MesloLGS NF Regular.ttf

        MesloLGS NF Bold.ttf

        MesloLGS NF Italic.ttf

        MesloLGS NF Bold Italic.ttf

🖥️ Set font di Windows Terminal:
Buka Settings → Ubuntu Profile

Set "fontFace": "MesloLGS NF"

6. Install Powerlevel10k
```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```
Lalu jalankan:
```bash
source ~/.zshrc
```
Jika diminta konfigurasi, ikuti wizard-nya.

