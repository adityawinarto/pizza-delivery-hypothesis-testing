# Pizza Delivery Hypothesis Testing

Modul 6 Data Sains – Analisis statistik inferensial pada dataset pengiriman pizza menggunakan uji t, ANOVA, dan korelasi untuk menjawab berbagai hipotesis operasional.

## 🎯 Tujuan Modul

- Menguji hipotesis terkait faktor-faktor yang memengaruhi durasi pengiriman pizza.
- Menggunakan uji statistik (uji t, ANOVA, korelasi Pearson) untuk mendukung keputusan bisnis.
- Mengidentifikasi variabel penting yang belum tersedia dan mengusulkan variabel tambahan untuk analisis lanjutan.

## 📌 Hipotesis & Metode

### 1. Pengaruh Jam Sibuk terhadap Waktu Pengiriman

- **Hipotesis:**
  - H0: Rata-rata waktu pengiriman pada jam sibuk tidak lebih lama dari jam non-sibuk.
  - H1: Rata-rata waktu pengiriman pada jam sibuk lebih lama dari jam non-sibuk.
- **Variabel:**
  - Is Peak Hour (binary: sibuk / tidak sibuk)
  - Delivery Duration (min) – numerik kontinu
- **Metode:** Independent samples t-test (one-tailed).

**Hasil Utama:**
- t-statistic ≈ 4.281, p-value ≈ 0.00003 → terdapat perbedaan signifikan.
- Waktu pengiriman lebih lama pada jam sibuk dibanding jam normal.

**Implikasi Keputusan:**
- Tambah kurir dan staf dapur di jam sibuk.
- Sesuaikan estimasi waktu pengantaran (ETA) agar lebih realistis.
- Pertimbangkan pengaturan kapasitas pesanan di peak hour.

---

### 2. Pengaruh Traffic Level terhadap Durasi Pengiriman

- **Hipotesis:**
  - H0: Rata-rata waktu pengiriman sama untuk semua level traffic.
  - H1: Setidaknya ada satu level traffic dengan rata-rata waktu pengiriman berbeda.
- **Variabel:**
  - Traffic Level (Low, Medium, High) – kategorikal
  - Delivery Duration (min) – numerik kontinu
- **Metode:** One-way ANOVA.

**Hasil Utama:**
- F-statistic ≈ 252.67, p-value ≈ 0.00000 → perbedaan rata-rata antar level traffic signifikan.
- Traffic Level berpengaruh kuat terhadap lama pengiriman.

**Implikasi Keputusan:**
- Terapkan strategi rute dan ETA berbeda berdasarkan kondisi lalu lintas.
- Gunakan informasi traffic untuk alokasi kurir yang lebih adaptif.
- Kembangkan sistem estimasi waktu berbasis level traffic.

---

### 3. Pengaruh Jumlah Topping terhadap Waktu Pengiriman

- **Hipotesis:**
  - H0: Tidak ada hubungan linear antara jumlah topping dan waktu pengiriman.
  - H1: Ada hubungan linear positif antara jumlah topping dan waktu pengiriman.
- **Variabel:**
  - Toppings Count – numerik kontinu
  - Delivery Duration (min) – numerik kontinu
- **Metode:** Korelasi Pearson.

**Hasil Utama:**
- r ≈ 0.558, p-value ≈ 0.00000 → hubungan positif cukup kuat dan signifikan.
- Semakin banyak topping, semakin lama waktu pengiriman (karena waktu persiapan bertambah).

**Implikasi Keputusan:**
- Sesuaikan estimasi waktu berdasarkan kompleksitas topping.
- Pertimbangkan batas variasi topping saat jam sibuk.
- Pertimbangkan biaya tambahan untuk pesanan dengan topping banyak.

---

### 4. Pengaruh Metode Pembayaran terhadap Kecepatan Pengiriman

- **Hipotesis:**
  - H0: Rata-rata waktu pengiriman dengan pembayaran digital tidak lebih cepat dari tunai.
  - H1: Rata-rata waktu pengiriman dengan pembayaran digital lebih cepat dari tunai.
- **Variabel:**
  - Payment Category (Online vs Offline) – dikotomis
  - Delivery Duration (min) – numerik kontinu
- **Metode:** Independent samples t-test (one-tailed).

**Hasil Utama:**
- t-statistic ≈ -0.460, p-value ≈ 0.64591 → tidak signifikan.
- Metode pembayaran tidak berpengaruh signifikan pada lama pengiriman.

**Implikasi Keputusan:**
- Tidak perlu mengubah proses pengiriman berdasarkan metode pembayaran.
- Pelanggan bebas memilih metode pembayaran tanpa mempengaruhi ETA.
- Fokus optimasi di faktor lain (traffic, jarak, topping, jam sibuk).

---

### 5. Pengaruh Jarak Pengiriman terhadap Waktu Pengiriman

- **Hipotesis:**
  - H0: Tidak ada hubungan linear antara jarak dan waktu pengiriman.
  - H1: Ada hubungan linear positif antara jarak dan waktu pengiriman.
- **Variabel:**
  - Distance (km) – numerik kontinu
  - Delivery Duration (min) – numerik kontinu
- **Metode:** Korelasi Pearson.

**Hasil Utama:**
- r ≈ 0.932, p-value ≈ 0.00000 → hubungan positif sangat kuat dan signifikan.
- Semakin jauh jarak, semakin lama waktu pengiriman.

**Implikasi Keputusan:**
- Gunakan jarak sebagai faktor utama dalam perhitungan ETA.
- Buat zona tarif/layanan berdasarkan jarak (near, mid, far).
- Optimalkan rute dan penugasan kurir per zona pengiriman.

---

## 🌱 Variabel Tambahan yang Diusulkan

Beberapa variabel penting yang diusulkan untuk analisis lanjutan:

- **Jumlah Kurir Aktif:** untuk mengukur bottleneck SDM pada jam sibuk.
- **Kondisi Cuaca:** cerah/hujan/berkabut sebagai faktor eksternal pengiriman.
- **Volume Pesanan per Jam:** intensitas beban dapur dan kurir.
- **Zona Delivery & Route Accessibility:** karakteristik geografis dan kemudahan akses.
- **Kecepatan Rata-rata Kurir & Road Quality Index:** untuk memahami efek kondisi jalan.
- **Transaction Processing Time & Cash Handling Complexity:** untuk melihat efek proses pembayaran di lapangan.

Variabel-variabel ini dapat digunakan pada proyek lanjutan, misalnya untuk regresi multivariat atau sistem ETA berbasis machine learning.
