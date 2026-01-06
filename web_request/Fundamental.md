# Web Request

## HyperText Transfer Protocol (HTTP)

![alt text](/images/flow.png)

Komunikasi HTTP terdiri dari client dan server, di mana client meminta resource ke server. Server memproses request dan mengembalikan resource yang diminta. Port default untuk komunikasi HTTP adalah port 80, namun bisa diubah ke port lain tergantung konfigurasi web server. Request yang sama juga digunakan saat kita browsing ke berbagai website. Kita memasukkan Fully Qualified Domain Name (FQDN) sebagai Uniform Resource Locator (URL) untuk mencapai website yang diinginkan, misalnya www.hackthebox.com.

![alt text](/images/url.png)

## URL Components

| Komponen     | Contoh               | Deskripsi                                                                                                                                             |
| ------------ | -------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Scheme       | `http://` `https://` | Digunakan untuk mengidentifikasi protokol yang diakses client, dan diakhiri dengan titik dua serta double slash (`://`)                               |
| User Info    | `admin:password@`    | Komponen opsional yang berisi kredensial (dipisah titik dua `:`) untuk autentikasi ke host, dan dipisahkan dari host dengan tanda at (`@`)            |
| Host         | `inlanefreight.com`  | Host menunjukkan lokasi resource. Bisa berupa hostname atau alamat IP                                                                                 |
| Port         | `:80`                | Port dipisahkan dari Host dengan titik dua (`:`). Jika tidak ditentukan, scheme http default ke port 80 dan https default ke port 443                 |
| Path         | `/dashboard.php`     | Menunjuk resource yang diakses, bisa file atau folder. Jika tidak ada path, server mengembalikan index default (mis. index.html)                      |
| Query String | `?login=true`        | Query string diawali tanda tanya (`?`), terdiri dari parameter (mis. login) dan nilai (mis. true). Banyak parameter dipisahkan dengan ampersand (`&`) |
| Fragments    | `#status`            | Fragment diproses browser di sisi client untuk menemukan bagian tertentu dalam resource utama (mis. header atau section pada halaman)                 |

> **Catatan:** Memahami komponen URL sangat penting untuk keamanan web dan penanganan request. Setiap komponen berperan penting dalam cara browser dan server berkomunikasi.
