# Promise

Javascript adalah bahasa yang *asynchronus* secara native. Operasi yang memiliki *delay* seperti IO dilakukan dengan tidak memblock main thread. Fungsi yang dijalankan secara async, hasilnya tidak akan langsung didapatkan melainkan *nanti*. Fungsi async ini biasanya mengembalikan *Promise*. 

Ilustrasi Promise
> - Joni        : "Pak pesen nasi goreng yak"
> - Mang Nasgor : "Siap, ditunggu yaa"
> - *Sambil menunggu nasi goreng dibuat, Joni berbalas pesan dengan rekan wanitanya. Beberapa saat kemudian...*
> - Mang Nasgor : "Mas, ini nasi gorengnya."
> - Joni        : "Oke, makasih pak.."

Dari ilustrasi tersebut, ada dua operasi. Operasi pertama *pembuatan nasi goreng* dan operasi kedua *berbalas pesan*. Operasi pertama tidak **memblock** operasi kedua, maka operasi pertama ini termasuk *async*. 

Pada javascript, untuk membuat fungsi menjadi async operasi di dalamnya dibungkus ke dalam Promise. Pada contoh berikut fungsi `scaryClown` memakan waktu 2 detik untuk selesai dijalankan. Maka, kita dapat bungkus ke dalam Promise.
```js
function scaryClown() {
  // returns a Promise
  return new Promise(() => {
    setTimeout(() => {
      console.log("🤡");
    }, 2000);
  });
}
```

Lalu kita coba panggil fungsi tersebut.
```js
scaryClown();
console.log("Gua duluan");
```
Maka yang muncul duluan adalah `Gua duluan`, lalu `🤡`.

# Async Await

Terkadang, kita perlu untuk menunggu hasil operasi async tersebut, sebelum melakukan operasi selanjutnya. Dengan javascript kita dapat menggunakan *async-await*. Async Await ini membuat fungsi yg kita dapat menunggu fungsi async sebelum melanjutkan operasi atau **memblock** fungsi async tersebut.

Pada contoh berikut, kita akan membuat fungsi memanggil API ke server `jsonplaceholder`. Hasil balikan dari fungsi tersebut akan dipakai untuk proses looping dan memprint title setiap iterasi nya.

```js
const https = require('https');
const url = 'https://jsonplaceholder.typicode.com/posts';

function fetchPost() {
    return new Promise((resolve, reject) => {
        https.get(url, res => {
            if res.statusCode != 200 {
                reject(new Error('failed'))
            }

            res.setEncoding('utf8')
            
            let body = ''
            res.on('data', data => {
                body += data
            })
            
            res.on('end', () => {
                body = JSON.parse(body)
                resolve(body)
            })

        }).on('error', (err) => reject(err))
    })
}
```

Lalu kita panggil fungsi `fetchPost` dengan keyword `async` dan lakukan `await` pada `fetchPost`
```js
async function main() {
    try {
        const data = await fetchPost()
        data.forEach(d => {
            console.log(d.title)
        })
    } catch (err) {
        console.error(err)
    }
}

main()
```