# Arrays
Array adalah kumpulan data dengan tipe yang sama. Sifat array pada javascript adalah dinamis, kita tidak perlu menentukan panjang suatu array. Berikut contoh deklarasi array

```js
// define an array var
let arr = [0, 1, 2];
```

Array juga memiliki fungsi built-in untuk melakukan modifikasi seperti push dan pop.

```js
// add another value to the array
arr.push(4);

console.log(arr);

// remove the last index of the array twice
arr.pop();
arr.pop();

console.log(arr);
```
