# Advprog Module 9 Tutorial
Hadyan Fachri\
2306245030\
Advprog A

## Reflection
**a. How much data your publisher program will send to the message broker in one run?**

- program publisher mengirim **5** pesan/event ke message broker (RabbitMQ) dalam satu kali eksekusi (cargo run). Setiap pesan berisi struktur data UserCreatedEventMessage dengan dua field:
    - `user_id`: String (contoh: "1", "2", dst.).
    - `user_name`: String (contoh: "2306245030-Amir", "2306245030-Budi", dst.).

- Publisher memanggil publish_event sebanyak 5 kali dengan data berbeda. Setiap pesan dikirim ke channel/topic bernama "user_created". Subscriber yang terhubung ke channel yang sama akan menerima pesan-pesan ini.

**b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?**

- URL ini adalah alamat koneksi ke RabbitMQ (message broker), dan kemiripannya di kedua program memiliki makna sebagai berikut:

    - Protokol `amqp`:
    Protokol standar untuk komunikasi dengan message broker (RabbitMQ).

    - Kredensial `guest:guest`:\
    Username: guest (default RabbitMQ).\
    Password: guest (default RabbitMQ).\
    Digunakan untuk autentikasi ke broker.

    - `localhost:5672`:
        - `localhost`: Broker berjalan di mesin lokal (komputer yang sama dengan program).
        - `5672`: Port default AMQP untuk koneksi ke RabbitMQ.

## Image
**Screenshot setelah menjalankan RabbitMQ**
![alt text](image.png)

**Setelah menjalankan cargo run publisher dan subscriber**
Yang bisa disimpulkan dari gambar ini, komunikasi antara publisher, subscriber maupun RabbitMQ berhasil. Publisher mengirim event berupa pesan ke RabbitMQ lalu subscriber menerimanya.
![alt text](image-1.png)

**Setelah menjalankan cargo run di terminal publisher kembali dan memperhatikan Chart pada RabbitMQ**
Yang bisa saya simpulkan dari gambar ini adalah setiap perintah cargo run pada terminal publisher dijalankan, chart pada RabbitMQ menghasilkan garis ungu dan garis kuning sebagai penanda data telah dikirim dan diterima.
![alt text](image-3.png)