## Home Assistant OS MiniDLNA Add-on

#### MiniDLNA (ReadyMedia) server for Home Assistant OS

This add-on allows you to run a DLNA/UPnP media server directly inside Home Assistant OS using the Supervisor add-on system. It serves media files from your configured folders to DLNA-compatible devices such as Smart TVs, media players, and consoles.

---

### 📌 What This Add-on Does

- Runs MiniDLNA inside Home Assistant OS
- Shares audio, video, and photo folders over DLNA
- Automatically advertises the server on your local network
- Works with any DLNA/UPnP compatible client

This add-on is intended only for Home Assistant OS / Supervised installations.

---

### 🚀 Installation

**1.** Open **Home Assistant**

**2.** Go to **Settings → Add-ons → Add-on Store**

**3.** Click ⋮ **(top right) → Repositories**

**4.** Add this repository URL

**5.** Install **MiniDLNA Add-on**

**6.** Start the add-on

**7.** (Optional) Enable **Start on boot** and **Watchdog**

---

### ⚙️ Configuration

Example configuration:
```
media_dir: A,/media/music;V,/media/video;P,/media/pictures
options: ""
friendly_name: "Home Assistant DLNA"
```

---

`media_dir`

Defines which directories will be scanned and shared.

Format:
```
TYPE,/path;TYPE,/path
```
Where TYPE can be:

- `A` – Audio
- `V` – Video
- `P` – Pictures

Example:
```
A,/media/music;V,/media/movies
```
You can use:
- `/media` – Home Assistant media folder
- `/share` – Shared folder
- External mounted drives (if mounted in HA OS)

---

`options`

Optional additional MiniDLNA flags.

Examples:

- `-d` → debug mode
- `-R` → force full rescan
- `-p 8201` → custom port

`friendly_name`

Sets how the DLNA server appears on your network.

---

### 🌐 Network Behavior

After starting:
- MiniDLNA scans configured folders
- It announces itself via UPnP
- Devices on the same LAN will detect it automatically

No Home Assistant integration is required — this is a standalone DLNA server.

---

### 🛠 Tips

- Ensure your media folders contain supported formats
- Large libraries may take time during first scan
- If media does not appear, restart the add-on or use -R option
- Make sure your TV/device is on the same subnet

---

#### 🧱 Requirements

- Home Assistant OS or Supervised installation
- Supervisor enabled
- Local network with DLNA-capable clients

---

#### 📜 License
Based on [MiniDLNA](https://minidlna.sourceforge.net/) (ReadyMedia).
See LICENSE file for details.
