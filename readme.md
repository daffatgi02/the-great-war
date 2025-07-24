
---

## 🎮 **Konsep The Great War**

---

## 🗺️ **Fitur Utama (Untuk Desain dan Gameplay)**

### 1. **Zona Hijau / Safe Area**

* Area yang bebas dari baku tembak (damage nonaktif).
* Fungsi: isi ulang peluru, beli senjata, beli baju, medical kit, beli armor.
* Lokasi strategis: bandara, markas militer, atau pelabuhan.

### 2. **Free Spawn Location**

* Pemain bisa memilih lokasi spawn secara bebas dari peta saat masuk.
* Fungsi: membuat tiap sesi unik dan unpredictable.

### 3. **Leaderboard & Crew System**

* **Leaderboard Individu**:

  * Berdasarkan kill terbanyak.
  * Killstreak, akurasi tembakan, waktu hidup terlama.

* **Leaderboard Crew (Tim)**:

  * Total kill crew.
  * Dominasi zona (lama menduduki red zone).
  * Bisa cari data leaderboard orang lain.

* **Nickname System**:

  * Format: `NICKNAME#TAG` (Contoh: ANJAI#404)

### 4. **Crew Features**

* Bisa buat crew atau join crew.
* Crew memiliki:

  * Channel radio otomatis (komunikasi push-to-talk).
  * Penanda posisi teammate di map (seperti mini radar).
  * Identitas visual (nickname + jarak dalam meter seperti Battlefield).
  * Crew benefit: bisa revive lebih cepat, share armor/ammo.

### 5. **Map Dynamic Indicators**

* Warzone status real-time:

  * **Zona Merah**: banyak kill terjadi (danger zone).
  * **Zona Kuning**: aktivitas sedang.
  * **Zona Putih**: baru selesai konflik.
* Notifikasi pop-up: “Tembakan berat terdengar di daerah X.”

### 6. **Friendly Fire Always ON**

* Semua pemain bisa kena damage dari siapapun, termasuk crew.
* Konsep: seperti dunia nyata, tidak ada immune system.

---

## 💰 **Ekonomi In-Game**

### 1. **Money System**

* Kill dapat uang (misalnya: 100 per kill).
* Loot dari peti, zona tertentu, atau rampasan player.
* Uang digunakan untuk beli:

  * Senjata eksklusif.
  * Tank, mobil lapis baja, pesawat tempur (akses di garage khusus).
  * Baju khusus crew / kosmetik.

---

## 🩹 **Role System (Support Gameplay)**

### Role yang bisa dipilih (opsional di awal game):

* **Assault**: Damage besar, bawa senjata berat.
* **Support**: Bawa banyak peluru, bisa lempar ammo ke orang lain.
* **Medic**: Bisa revive lebih cepat, bawa medical kit ekstra.
* **Recon**: Bisa tandai musuh (seperti drone), jangkauan radar lebih besar.

---

## 🧱 **Scope Developer - Detail Kebutuhan Teknis**

### A. **Core System & Infrastructure**

* Framework: QBCore atau ESX (pilih salah satu).
* Database: MySQL/SQLite.
* Authentication: nickname#tag sistem unik.
* Spawn Selector UI.
* Friendly fire system with health/armor rules:

  * 100 HP + 100 armor, max carry: 3 armor kit.

### B. **Map & Zone System**

* Red/Yellow/White zone markers (dynamic blip system).
* Notifikasi area konflik.
* Green zone logic (anti-damage + akses shop/garage).

### C. **Combat & Inventory**

* Senjata dengan durability.
* Ammo count system.
* Armor logic (auto-apply, max stack 3).
* Friendly fire ON always (event handler via damage event override).

### D. **Crew & Leaderboard**

* Sistem pembuatan crew.
* Auto-assign radio freq berdasarkan crew.
* Mini radar teammate (distance indicator).
* Crew chat / voice.
* Leaderboard backend (kill count, crew rank).

### E. **Economy & Shop System**

* Kill reward system.
* Shop (senjata, kendaraan, outfit).
* Peti lootable.
* Server-side anti-cheat basic logic (minimal exploit).

### F. **Role System**

* Class selection on spawn.
* Role-based ability (revive speed, ammo drop, radar boost).
* Visual indicator untuk setiap role.

---

## ✅ **Checklist Review Desain**

| Elemen                      | Status | Catatan                  |
| --------------------------- | ------ | ------------------------ |
| Zona hijau                  | ✅      | Butuh 2-3 lokasi         |
| Leaderboard crew & personal | ✅      | Include UI               |
| Friendly fire always ON     | ✅      | Custom event             |
| Map alert sistem warna      | ✅      | Update tiap 30 detik     |
| Crew radio & radar teammate | ✅      | Jarak + nickname tampil  |
| Role & kemampuan unik       | ✅      | Harus balance            |
| Spawn selector              | ✅      | UI interaktif            |
| Sistem uang & shop          | ✅      | Ekonomi dasar jalan dulu |


