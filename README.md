## Penjelasan Topologi

jaringan yang menghubungkan tiga kampus: **Kampus Citra Raya (CR)**, **Kampus Kebon Jeruk (KJ)**, dan **Kampus Harapan Indah (KHI)**. Berikut adalah penjelasan rinci dari topologi tersebut:

### 1. **Koneksi Antar Kampus melalui Internet**
   - Setiap kampus memiliki **Router** dengan IP publik masing-masing untuk membangun koneksi antar lokasi melalui **tunnel VPN**:
     - **Kampus Citra Raya (CR):** IP Publik 10.254.254.1/32
     - **Kampus Kebon Jeruk (KJ):** IP Publik 10.254.254.2/32
     - **Kampus Harapan Indah (KHI):** IP Publik 10.254.254.5/32

   - Tunnel digunakan untuk membuat jaringan privat yang aman di antara ketiga kampus, memungkinkan pertukaran data tanpa risiko akses eksternal.

---

### 2. **Jaringan di Setiap Kampus**
   #### a. **Kampus Citra Raya**
   - **Router CR** terhubung ke **Lab_Switch** untuk mendistribusikan koneksi ke perangkat dalam kampus.
   - **VLAN yang digunakan:**
     - **VLAN 10 (LAB-PC):** 10.2.10.1/24
     - **VLAN 20 (MHS - Mahasiswa):** 10.2.20.1/24
   - Perangkat yang terhubung:
     - **Lab_PC**: Komputer yang terhubung melalui kabel ke switch.
     - **Access Point:** Memberikan koneksi nirkabel untuk perangkat seperti **handphone** dan **laptop**.

   #### b. **Kampus Kebon Jeruk**
   - Menggunakan **Firewall** untuk mengamankan koneksi sebelum diteruskan ke **Lab_Switch**.
   - **IP Router KJ:** 10.254.1.9/30 dan 10.254.1.10/30
   - **VLAN yang digunakan:**
     - **VLAN 10 (LAB-PC):** 10.1.10.1/24
     - **VLAN 20 (MHS):** 10.1.20.1/24
   - Perangkat yang terhubung sama seperti Kampus CR (Lab_PC, Access Point, Handphone, dan Laptop).

   #### c. **Kampus Harapan Indah**
   - Konfigurasi serupa dengan Kampus Citra Raya, di mana **Router KHI** terhubung ke **Lab_Switch**.
   - **VLAN yang digunakan:**
     - **VLAN 10 (LAB-PC):** 10.3.10.1/24
     - **VLAN 20 (MHS):** 10.3.20.1/24
   - Perangkat:
     - **Lab_PC**: Terhubung melalui kabel.
     - **Access Point:** Untuk perangkat mobile seperti **handphone** dan **laptop**.

---

### 3. **Fungsi VLAN**
   - **VLAN 10 (LAB-PC):** Mengelompokkan perangkat yang digunakan di laboratorium komputer.
   - **VLAN 20 (MHS):** Digunakan untuk perangkat mahasiswa agar tidak tercampur dengan VLAN lainnya.
   - VLAN memberikan segmentasi jaringan, meningkatkan efisiensi, dan keamanan.

---

### 4. **Keunggulan Desain Topologi**
   - **Keamanan Data:** Menggunakan tunnel untuk koneksi antar kampus dan firewall di Kampus Kebon Jeruk.
   - **Segmentasi Jaringan:** VLAN memisahkan lalu lintas data berdasarkan pengguna atau fungsi.
   - **Skalabilitas:** Setiap kampus dapat menambah perangkat tanpa mengganggu konektivitas antar kampus.
   - **Akses Wireless:** Tersedia di setiap kampus melalui access point.
