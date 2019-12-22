# Variables & Identifiers

## Variables

Membuat variable pada javascript diawali dengan keyword `var, let, atau const`. Pada spesifikasi ECMA Script 2015, sudah jarang penggunaan keyword `var` lebih banyak digantikan oleh `let` atau `const`. Pada buku ini, akan menggunakan dua keyword itu saja. Berikut adalah contoh deklarasi variable

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

## Identifiers

`const` & `let` memiliki perbedaan fungsi. `let` digunakan untuk variable yang dapat diubah valuenya, sedangkan `const` digunakan untuk variable yang value nya tidak dapat diubah.

```js
const constVar = "constVar";
let letVar = "letVar",
  varVar = "varVar";

console.log("constVar: " + constVar);
console.log("letVar: " + letVar);
console.log("varVar: " + varVar);

// this would result in an error
// constVar = "newConstVar"

letVar = "newLetVar";
varVar = "newVarVar";

console.log("\nletVar: " + letVar);
console.log("varVar: " + varVar);

console.log("\nvar di dalam loop");
for (var i = 0; i < 2; ++i) {
  console.log("Nilai i: " + i);
}

console.log("var di luar loop, i: " + i);

console.log("\nlet di dalam loop");
for (let j = 0; j < 2; ++j) {
  console.log("Nilai j: " + j);
}

console.log("let di luar loop, j: " + j);
```
