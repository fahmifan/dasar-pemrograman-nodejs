# Object

Object adalah sebuah tipe data yang dapat menampung beberapa tipe data lain yg berbeda. Tidak seperti array, object tidak diakses dengan `index` melainkan dengan `key`. Key  ataupun value ini dapat diisi dengan tipe data seperti string, number, atau boolean. Contoh simple object

```js
let orang = {
    nama: 'miun',
    umur: 17,
    hobi: 'ngoding',
    aktif: true,
}
```
Pengaksesan object tersbut adalah denga menggunakan dot `.`
```js
console.log('nama orang: ', orang.nama)
```

Selain itu pengakses juga dapat menggunakan `object['key']`
```js
console.log('nama orang: ', orang['nama'])
```

Dengan object kita dapat membuat struktur data dengan mudah. Misal kita ingin membuat struktur untuk sebuah buku dalam perpustakaan, maka kita dapat membuat sbb:
```js
let buku = {
    judul: 'Dasar Pemgrograman Node Js',
    pengarang: 'miun173',
    tahunTerbit: 2019,
    topik: ['edukasi', 'pemrograman', 'node js', 'javascript'],
}
```
> Print semua item dalam topik
> ```buku.topik.forEach(b => { console.log(b) })```


Kita juga dapat membuat object kosong lalu menambahkan `key:value` sbb:
```js
// define an empty object
let obj = {};

console.log(obj);

// add a key value to the 'obj' var
obj.hello = "world";

console.log(obj);

// add another key value to the 'obj' var
obj["number"] = 1;

console.log(obj);

// delete a key value to the 'obj' var
delete obj.hello;

console.log(obj);
```
