# Tutorial Pemrograman Lanjut
oleh Brenda Po Lok Fahida




**Modul 5: Java Profiling**
---


### 📊 Optimisasi Performa API

Berikut ini adalah hasil optimisasi performa untuk beberapa endpoint pada aplikasi. Setelah dilakukan optimisasi, terdapat peningkatan kecepatan eksekusi untuk masing-masing endpoint.

### 🚀 Hasil Optimisasi

| Endpoint            | Sebelum Optimisasi (ms) | Setelah Optimisasi (ms) | Speedup (%) |
|---------------------|-----------------------|------------------------|------------|
| **All-Student**     | 17318                 | 9109                   | 47.4%      |
| **All-Student-Name**| 96                    | 94                     | 2.08%      |
| **Highest-GPA**     | 52                    | 48                     | 7.69%      |

### 📌 Analisis

- **All-Student** mengalami peningkatan signifikan dengan speedup sebesar **47.4%**, menunjukkan efisiensi yang lebih baik dalam pengambilan data mahasiswa beserta mata kuliahnya.
  <details><summary>Dokumentasi</summary>
    
    **Before Optimization**
   <img width="1440" alt="before optimize 1" src="https://github.com/user-attachments/assets/2181688a-5d92-4072-9a26-0035fa592b7f" />
    **Test Plan**
    <img width="1180" alt="Screenshot 2025-03-14 at 18 11 23" src="https://github.com/user-attachments/assets/234ed861-2cca-404c-839d-137116fcc705" />
    **After Optimization**
   <img width="1440" alt="optimize 1" src="https://github.com/user-attachments/assets/1b9721fe-ccff-4341-a09e-90f1239eab14" />

</details>

- **All-Student-Name** hanya mengalami peningkatan kecil sebesar **2.08%**, kemungkinan karena sebelumnya metode sudah cukup optimal.
  <details><summary>Dokumentasi</summary>
    
    **Before Optimization**
   <img width="1440" alt="before optimize 2" src="https://github.com/user-attachments/assets/185efb5f-e58a-421d-b45e-64e7e474c6d9" />

    **Test Plan**
    <img width="1152" alt="Screenshot 2025-03-14 at 18 22 35" src="https://github.com/user-attachments/assets/4f438f6e-d39d-4e9b-84ba-e47562296f9e" />

    **After Optimization**
  <img width="1440" alt="optimize 2" src="https://github.com/user-attachments/assets/9eff0bf8-3b54-48c9-9ac5-065ef7fbb436" />

</details>

- **Highest-GPA** mengalami peningkatan sebesar **7.69%**, yang membantu mempercepat pencarian mahasiswa dengan GPA tertinggi.
  <details><summary>Dokumentasi</summary>
    
    **Before Optimization**
  <img width="1440" alt="before optimize 3" src="https://github.com/user-attachments/assets/31c42565-f40e-41ed-850b-3d67a875e1ca" />

    **Test Plan**
  <img width="1149" alt="Screenshot 2025-03-14 at 18 32 47" src="https://github.com/user-attachments/assets/47fef2b2-fdbb-40ff-a76e-7c8c708e3c97" />

    **After Optimization**
  <img width="1440" alt="optimize 3" src="https://github.com/user-attachments/assets/473073b0-1b1f-459f-8337-c90bfc63b142" />

</details>



### 🔍 Kesimpulan
Optimisasi ini berhasil mengurangi waktu eksekusi, terutama pada endpoint **All-Student**. 


<d>



**Reflection**
--- 

<details><summary>Refleksi 1</summary>
  
> What is the difference between the approach of performance testing with JMeter and profiling with IntelliJ Profiler in the context of optimizing application performance?

- **JMeter** digunakan untuk melakukan **pengujian performa berbasis beban** (load testing) dengan mensimulasikan banyak pengguna yang mengakses aplikasi secara bersamaan. Ini membantu dalam **mengevaluasi kapasitas aplikasi**, menemukan batas skalabilitas, dan mengidentifikasi potensi bottleneck pada tingkat infrastruktur.  
- **IntelliJ Profiler**, di sisi lain, digunakan untuk **profiling kode pada level aplikasi**. Ini membantu **menganalisis penggunaan CPU, memori, thread, dan eksekusi metode secara mendalam** untuk menemukan titik lemah dalam kode, seperti metode yang terlalu lambat atau alokasi memori yang berlebihan.  
</details>

<details><summary>Refleksi 2</summary>
  
> How does the profiling process help you in identifying and understanding the weak points in your application?

Profiling memberikan insight yang lebih detail dibandingkan pengujian performa biasa dengan cara:  
1. **Melacak metode atau fungsi yang menghabiskan terlalu banyak waktu eksekusi** → membantu menemukan bagian kode yang perlu dioptimasi.  
2. **Menganalisis alokasi memori dan garbage collection** → mengidentifikasi kebocoran memori atau penggunaan memori yang tidak efisien.  
3. **Melihat penggunaan thread dan concurrency issues** → mendeteksi potensi deadlock atau thread yang tidak optimal.  
</details>

<details><summary>Refleksi 3</summary>
  
> Do you think IntelliJ Profiler is effective in assisting you to analyze and identify bottlenecks in your application code?

Ya, IntelliJ Profiler cukup efektif dalam membantu mengidentifikasi bottleneck pada kode aplikasi. Dengan fitur seperti **CPU profiling, memory analysis, dan thread monitoring**, kita bisa mengetahui bagian mana dari kode yang perlu diperbaiki. Namun, **profiling lebih efektif untuk analisis di lingkungan pengembangan**, sedangkan pengujian performa dengan JMeter lebih cocok untuk simulasi kondisi dunia nyata.  
</details>

<details><summary>Refleksi 4</summary>
  
> What are the main challenges you face when conducting performance testing and profiling, and how do you overcome these challenges?

1. **Data yang tidak konsisten antara pengujian performa dan profiling** → Bisa terjadi karena perbedaan lingkungan (dev vs production). Solusinya adalah **menjalankan profiling dalam kondisi yang menyerupai produksi** sebanyak mungkin.  
2. **Overhead pada Profiling** → Profiling bisa memperlambat eksekusi aplikasi. Cara mengatasinya adalah dengan **menggunakan sampling profiler** daripada instrumentasi penuh jika tidak perlu detail granular.  
3. **Menafsirkan hasil profiling yang kompleks** → Memahami output dari profiler bisa sulit. **Menggunakan filter dan visualisasi yang tersedia dalam IntelliJ Profiler** bisa membantu memperjelas insight yang didapat.  
</details>

<details><summary>Refleksi 5</summary>
  
> What are the main benefits you gain from using IntelliJ Profiler for profiling your application code?

- **Identifikasi bottleneck secara detail** hingga tingkat metode.  
- **Memantau penggunaan CPU, memori, dan thread secara real-time**.  
- **Membantu debugging masalah performa seperti memory leaks dan deadlocks**.  
- **Dapat langsung dijalankan dalam IntelliJ tanpa perlu alat tambahan**.  
</details>

<details><summary>Refleksi 6</summary>
  
> How do you handle situations where the results from profiling with IntelliJ Profiler are not entirely consistent with findings from performance testing using JMeter?

Jika hasil dari profiling tidak sesuai dengan temuan JMeter, beberapa langkah yang bisa dilakukan:  
1. **Periksa lingkungan pengujian** → Pastikan lingkungan saat profiling mirip dengan lingkungan saat pengujian performa (misalnya, jumlah thread, beban aplikasi).  
2. **Gunakan tracing tambahan** → Gunakan logging atau alat lain seperti **Application Performance Monitoring (APM)** untuk validasi lebih lanjut.  
3. **Lakukan profiling pada skenario beban tinggi** → Menjalankan profiler saat aplikasi berada di bawah beban yang tinggi bisa memberikan hasil yang lebih representatif.  
</details>

<details><summary>Refleksi 7</summary>
  
> What strategies do you implement in optimizing application code after analyzing results from performance testing and profiling? How do you ensure the changes you make do not affect the application's functionality?

1. **Optimasi algoritma** → Misalnya mengganti algoritma pencarian atau sorting yang lebih efisien.  
2. **Caching data yang sering diakses** untuk mengurangi beban pada database atau service eksternal.  
3. **Menggunakan asynchronous processing** untuk tugas yang tidak harus berjalan secara sinkron.  
4. **Memperbaiki query database yang lambat** dengan indexing atau query optimization.  
5. **Memantau setelah perubahan dilakukan** → Setelah mengimplementasikan optimasi, perlu dilakukan regresi testing dan pengujian ulang untuk memastikan **tidak ada perubahan fungsional yang tidak diinginkan**.  
</details>
 
