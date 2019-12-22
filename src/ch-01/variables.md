# Variables

Membuat variable pada javascript diawali dengan keyword `var, let, atau const`. Pada spesifikasi ECMA Script 2015, sudah jarang penggunaan keyword `var` lebih banyak digantikan oleh `let` atau `var`. Pada buku ini, akan menggunakan dua keyword itu saja. Berikut adalah contoh deklarasi variable

```js
const boolVar = false,
  numVar = 42,
  bigIntVar = 42n,
  strVar = "hello",
  undefinedVar = undefined,
  nullVar = null,
  objVar = {};

console.log("boolVar: " + typeof boolVar);
console.log("numVar: " + typeof numVar);
console.log("bigIntVar: " + typeof bigIntVar);
console.log("strVar: " + typeof strVar);
console.log("undefinedVar: " + typeof undefinedVar);
console.log("nullVar: " + typeof nullVar);
console.log("objVar: " + typeof objVar);
```

Karena javascript adalah dynamic language, maka tipe data tidak perlu dituliskan dan akan dievaluasi saat baris kode dijalankan (runtime).