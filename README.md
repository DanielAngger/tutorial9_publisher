# Tutorial 9 Publisher Reflection

<details>
<summary>How much data your publisher program will send to the message broker in one run?</summary>

> Program publisher ini akan mengirim 5 buah pesan ke message broker. Setiap pesan itu adalah struct UserCreatedEventMessage yang berisi user_id: sebuah string (contoh: "1", "2", dst) dan user_name: string juga (contoh: "129500004y-Amir"). Secara total, program ini mengirim 5 pesan ke message broker dalam satu kali dijalankan.

</details>

<details>
<summary>The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?</summary>

> Karena publisher dan subscriber sama-sama menggunakan URL ini, maka mereka terhubung ke server RabbitMQ yang sama, yaitu localhost. Jadi, ketika publisher ini kirim pesan ke queue "user_created", maka subscriber yang sedang listen di queue yang sama akan menerima pesan-pesan tersebut.

</details>

<details>
<summary>Screenshot of running RabbitMQ.</summary>

> ![Alt text](image.png)

</details>

<details>
<summary>Screenshot of sending and processing event.</summary>

> ![Alt text](image-1.png)

> Ketika ‘cargo run’ dieksekusi pada publisher, publisher mengirimkan 5 event ke message broker. Event tersebut kemudian dikonsumsi dan diproses oleh subscriber.
</details>


<details>
<summary>Screenshot of monitoring chart based on publisher.</summary>

> ![Alt text](image-2.png)

> Bisa dilihat pada chart di atas, ada "duri" yang terlihat di selang waktu tertentu. Duri tersebut menandakan kalau pada waktu tersebut, publisher sedang dieksekusi, yang mengakibatkan subscriber memproses event tersebut.

</details>