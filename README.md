# RTOS Exercise 4
Proyek ini bertujuan untuk mengontrol beberapa LED menggunakan mikrokontroler STM32 dengan FreeRTOS. Proyek ini memanfaatkan FreeRTOS untuk mengontrol empat LED (Biru, Hijau, Merah, dan Kuning) yang terhubung ke STM32. Dua task utama diimplementasikan yaitu FlashGreenLedTask dan FlashRedLedTask.


## Cara Kerja 
1. Task FlashGreenLedTask mengontrol LED biru dan hijau dengan pola seperti berikut.
- Menyalakan LED Biru dan mengedipkan LED Hijau dengan frekuensi 20 Hz selama 4 detik. Kemudian mematikan LED Hijau dan Biru, lalu menunggu atau jeda selama 6 detik sebelum mengulangi siklus.
2. Task FlashRedLedTask mengontrol LED kuning dan merah dengan pola seperti berikut.
- Menyalakan LED Kuning dan mengedipkan LED Merah dengan frekuensi 20 Hz selama 0,5 detik. Kemudian mematikan LED Merah dan Kuning, lalu menunggu atau jeda selama 1,5 detik sebelum mengulangi siklus.

Pada proyek ini, FlashRedLedTask memiliki prioritas lebih tinggi dibandingkan dengan FlashGreenLedTask. Dengan hal ini, maka FlashRedLedTask akan selalu dijalankan terlebih dahulu oleh FreeRTOS jika kedua task dalam keadaan siap. 


## Hardware 
![RTOS_Exercise 4](https://github.com/user-attachments/assets/cc0972f9-3e15-4d39-934e-4ac2baa23c8f)
![RTOS_Exercise 4](https://github.com/user-attachments/assets/9ed970e6-2eef-4569-83d3-818812091cb4)


## Output Proyek
* LED hijau akan berkedip secara teratur sebanyak 80 kali, diikuti dengan LED biru yang menyala selama 6 detik.
* LED merah akan berkedip sebanyak 10 kali, diikuti dengan LED kuning yang mati.
* Kedua task ini berjalan secara bersamaan dengan jadwal yang mengatur kapan masing-masing LED akan berkedip.
