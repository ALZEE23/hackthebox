## CURL

cURL (client URL) is a command-line tool and library that primarily supports HTTP along with many other protocols. This makes it a good candidate for scripts as well as automation, making it essential for sending various types of web requests from the command line, which is necessary for many types of web penetration tests.

## Tabel Fungsi/Option cURL (Ringkas)

| Opsi                          | Fungsi                                  | Contoh                                                        | Catatan                                                        |
| ----------------------------- | --------------------------------------- | ------------------------------------------------------------- | -------------------------------------------------------------- |
| `-o <file>`                   | Simpan output ke file                   | `curl -o index.html https://example.com`                      | Menimpa file jika sudah ada                                    |
| `-O`                          | Simpan output dengan nama file dari URL | `curl -O https://example.com/file.zip`                        | Menggunakan nama file asli                                     |
| `-L`                          | Ikuti redirect                          | `curl -L http://example.com`                                  | Mengikuti 3xx                                                  |
| `-I`                          | Hanya header (HEAD)                     | `curl -I https://example.com`                                 | Tanpa body                                                     |
| `-i`                          | Sertakan header dalam output            | `curl -i https://example.com`                                 | Header + body                                                  |
| `-v`                          | Verbose/debug                           | `curl -v https://example.com`                                 | Lihat detail request/response                                  |
| `-s`                          | Silent (tanpa progress)                 | `curl -s https://example.com`                                 | Sering dikombinasikan dengan `-S`                              |
| `-S`                          | Tampilkan error saat `-s`               | `curl -sS https://example.com`                                | Menampilkan error saja                                         |
| `-X <METHOD>`                 | Tentukan HTTP method                    | `curl -X POST https://example.com`                            | Default: GET                                                   |
| `-d <data>`                   | Kirim data (POST/PUT)                   | `curl -d "user=alzee" https://example.com/login`              | Otomatis set `Content-Type: application/x-www-form-urlencoded` |
| `-H <header>`                 | Tambah header                           | `curl -H "Authorization: Bearer <token>" https://example.com` | Bisa diulang                                                   |
| `-u <user:pass>`              | Basic auth                              | `curl -u admin:admin https://example.com`                     | Dapat dipakai dengan `-H` untuk auth lain                      |
| `-k`                          | Abaikan TLS cert error                  | `curl -k https://self-signed.badssl.com`                      | Hati-hati di produksi                                          |
| `-b <cookie>`                 | Kirim cookie                            | `curl -b "session=abc" https://example.com`                   | Bisa juga pakai file cookie                                    |
| `-c <cookiefile>`             | Simpan cookie ke file                   | `curl -c cookies.txt https://example.com`                     | Dipakai bersama `-b`                                           |
| `--data-raw <data>`           | Kirim data mentah                       | `curl --data-raw "a=1&b=2" https://example.com`               | Tidak memproses @file                                          |
| `--data-urlencode <data>`     | URL encode data                         | `curl --data-urlencode "q=hack the box" https://example.com`  | Aman untuk spasi/simbol                                        |
| `-F <name=content>`           | Form multipart                          | `curl -F "file=@test.txt" https://example.com/upload`         | Untuk upload file                                              |
| `--json <data>`               | Kirim JSON                              | `curl --json '{"user":"alzee"}' https://example.com/api`      | Set header `Content-Type: application/json`                    |
| `-A <ua>`                     | User-Agent                              | `curl -A "Mozilla/5.0" https://example.com`                   | Spoof UA                                                       |
| `-e <url>`                    | Referer                                 | `curl -e "https://google.com" https://example.com`            | Set Referer                                                    |
| `--proxy <url>`               | Gunakan proxy                           | `curl --proxy http://127.0.0.1:8080 https://example.com`      | Cocok dengan Burp                                              |
| `--resolve <host:port:ip>`    | Override DNS                            | `curl --resolve example.com:443:1.2.3.4 https://example.com`  | Hanya untuk request ini                                        |
| `-m <seconds>`                | Timeout maksimum                        | `curl -m 10 https://example.com`                              | Batasi waktu total                                             |
| `--connect-timeout <seconds>` | Timeout koneksi                         | `curl --connect-timeout 3 https://example.com`                | Hanya fase koneksi                                             |
| `-r <range>`                  | Download range                          | `curl -r 0-99 https://example.com/file.bin`                   | Partial content                                                |
| `-C -`                        | Resume download                         | `curl -C - -O https://example.com/file.zip`                   | Lanjutkan unduhan                                              |
| `-w <format>`                 | Output format khusus                    | `curl -w "HTTP: %{http_code}\n" https://example.com`          | Lihat status code                                              |
| `-D <file>`                   | Simpan header ke file                   | `curl -D headers.txt https://example.com`                     | Header saja                                                    |
| `--compressed`                | Minta konten terkompresi                | `curl --compressed https://example.com`                       | Mengirim header `Accept-Encoding`                              |

```bash
ALZEE23@htb[/htb]$ curl inlanefreight.com

<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
...SNIP...
```
