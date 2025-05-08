# Tutorial 9 Publisher Reflection

<details>
<summary>How much data your publisher program will send to the message broker in one run?</summary>

> Program publisher ini akan mengirim 5 buah pesan ke message broker. Setiap pesan itu adalah struct UserCreatedEventMessage yang berisi user_id: sebuah string (contoh: "1", "2", dst) dan user_name: string juga (contoh: "129500004y-Amir"). Secara total, program ini mengirim 5 pesan ke message broker dalam satu kali dijalankan.

</details>

<details>
<summary>The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?</summary>

> Karena publisher dan subscriber sama-sama menggunakan URL ini, maka mereka terhubung ke server RabbitMQ yang sama, yaitu localhost. Jadi, ketika publisher ini kirim pesan ke queue "user_created", maka subscriber yang sedang listen di queue yang sama akan menerima pesan-pesan tersebut.

</details>