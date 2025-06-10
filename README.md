# Proyek Klasifikasi Tumor Otak dengan Transfer Learning VGG16
Proyek ini bertujuan untuk mengklasifikasikan jenis tumor otak menggunakan teknik transfer learning dengan model VGG16 yang diimplementasikan menggunakan TensorFlow dan Keras. Dataset yang digunakan terdiri dari gambar tumor otak yang dikategorikan ke dalam beberapa kelas: glioma, meningioma, notumor (tidak ada tumor), dan pituitary.

Model ini dilatih dan dievaluasi untuk memberikan prediksi yang akurat terhadap jenis tumor berdasarkan gambar MRI otak.

# ⚙️ Instalasi
Untuk menjalankan proyek ini, Anda perlu menginstal beberapa dependensi utama. Berikut adalah perintah instalasi yang digunakan dalam proyek:
pip install tensorflow scikit-learn matplotlib seaborn pillow opencv-python

Dependensi utama yang digunakan:
TensorFlow : Framework deep learning dan transfer learning
scikit-learn	: Evaluasi model dan metrik klasifikasi
matplotlib	: Visualisasi data dan hasil
seaborn	: Visualisasi statistik dan heatmap
pillow (PIL)	: Pengolahan gambar
opencv-python	: Pengolahan gambar dan augmentasi

# 🚀 Cara Penggunaan
1. Persiapan Dataset
 - Dataset berbentuk file ZIP yang berisi gambar tumor otak harus diunggah ke Google Drive.
 - File ZIP diekstrak ke direktori kerja di Google Colab.
 - Dataset terdiri dari beberapa folder yang berisi gambar untuk masing-masing kelas tumor.

2. Mount Google Drive di colab
   from google.colab import drive
   drive.mount('/content/drive')

3. Jalankan Script .ipynb
Jalankan script finish_proyek_brain_tumor.py yang berisi seluruh pipeline mulai dari persiapan data, augmentasi, pelatihan model, hingga evaluasi.

# 🗂️ Persiapan Data
- Dataset dari beberapa sumber digabungkan ke dalam satu folder combined.
- Kelas yang digunakan: glioma, meningioma, notumor, dan pituitary.
- Data dibagi menjadi data latih dan data uji.
- Augmentasi gambar dilakukan menggunakan ImageDataGenerator untuk meningkatkan variasi data latih.

# 🏗️ Arsitektur Model
- Model dasar menggunakan VGG16 pretrained pada ImageNet tanpa layer top (fully connected).
- Layer tambahan yang ditambahkan:
  - Global Average Pooling 2D
  - Dense layer dengan aktivasi ReLU dan dropout untuk regularisasi
  - Batch Normalization
  - Output layer dengan softmax untuk klasifikasi multi-kelas
- Optimizer yang digunakan adalah Adam dengan learning rate yang disesuaikan.
- Callback seperti EarlyStopping, ModelCheckpoint, dan ReduceLROnPlateau digunakan untuk mengoptimalkan pelatihan.

# 📊 Evaluasi Model
- Model dievaluasi menggunakan metrik akurasi, confusion matrix, dan classification report.
- Visualisasi hasil evaluasi menggunakan heatmap confusion matrix dan grafik akurasi serta loss selama pelatihan.
- Model terbaik disimpan berdasarkan performa validasi.

# 📌 Catatan Tambahan
- Proyek ini dioptimalkan untuk dijalankan di Google Colab dengan akses ke Google Drive.
- Pastikan dataset sudah diupload ke Google Drive dan path file ZIP sudah disesuaikan.
- Script sudah mencakup proses lengkap dari ekstraksi data, pelatihan, hingga evaluasi.
