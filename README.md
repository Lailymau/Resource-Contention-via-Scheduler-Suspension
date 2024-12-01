# Exercise 6 - Eliminating Resource Contention by Suspending the Scheduler

## 📜 Deskripsi Proyek
Proyek ini menunjukkan implementasi RTOS (Real-Time Operating System) pada mikrokontroler STM32 untuk mengelola tugas-tugas LED secara bersamaan. Dengan menggunakan FreeRTOS, sistem ini memungkinkan pengendalian LED dengan tingkat prioritas yang berbeda, sehingga memperlihatkan kemampuan multitasking dan sinkronisasi sumber daya bersama.

---

## 🎯 Tujuan Proyek
- Mengimplementasikan multitasking menggunakan FreeRTOS.  
- Mensinkronkan sumber daya bersama antar thread.  
- Membuat tugas untuk mengontrol kecepatan berkedip LED dengan prioritas yang berbeda.

---

## 📂 Node Diagram
![image](https://github.com/user-attachments/assets/cf2f3053-5879-4e3c-a2cb-1b0d58f35c8d)

---

## 🛠️ Peralatan dan Perangkat
- 💻 **Perangkat Lunak**: STM32CubeIDE, FreeRTOS  
- 🔧 **Perangkat Keras**: Board STM32 Nucleo, LED, Kabel Jumper  

---

## 📋 Langkah Implementasi
### 🟢 **Persiapan Lingkungan**
- Buka file `.ioc` menggunakan STM32CubeMX untuk mengonfigurasi periferal (GPIO dan FreeRTOS).  
- Hasilkan kode dan buka di STM32CubeIDE.

### 🟡 **Implementasi Kode**
- **Definisikan Pin GPIO** untuk LED di fungsi `MX_GPIO_Init`.  
- **Atur Prioritas Tugas**:
  - LED Hijau: Tugas dengan prioritas tinggi.  
  - LED Merah: Tugas dengan prioritas sedang.  
  - LED Kuning: Tugas dengan prioritas rendah.  

### 🔵 **Tambahkan Fitur RTOS**
- Buat *task* menggunakan fungsi `xTaskCreate`.  
- Atur *delay* untuk setiap tugas dengan `vTaskDelay` agar LED berkedip pada interval berbeda.  
- Pastikan konfigurasi kernel RTOS diaktifkan pada `.ioc`.

---

## 🌟 Hasil yang Diharapkan
- RTOS berhasil mengelola multitasking tanpa konflik antar tugas.
- LED berkedip dengan kecepatan yang sesuai dengan prioritas tugas:
  - LED Hijau berkedip tercepat.
  - LED Merah berkedip sedang.
  - LED Kuning berkedip paling lambat.

---

## 🧪 Hasil Percobaan Normal
https://github.com/user-attachments/assets/931b29b7-195e-4839-a659-44cd1663e8ef

---

## 🧪 Hasil Percobaan Normal Konflik
https://github.com/user-attachments/assets/376253f7-56d8-4cc5-ab7e-7fd7f06c23e3
