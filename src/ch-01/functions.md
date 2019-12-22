# Functions
Deklarasi *fungsi* pada javascript adalah sebagai berikut
```js
function print() {
    console.log('Hello World')
}

// pemanggilan fungsi
print()
```

*Fungsi* juga dapat mengembalikan nilai
```js
function add(x, y) {
    return x + y
}

const result = add(3, 4)
console.log(result)
// output: 7
```

*Fungsi* memiliki *closure* yaitu dapat menggunakan variable di luar scope *fungsi* nya

```js
const num = 2.0
function divideByNum(x) {
    return x / num
}

const result = divideByNum(10)
console.log(result)
// output 5
```

Parameter dari *fungsi* ini adalah tipe data valid + *fungsi* yang sering disebut sebagai *callback*
```js
// jumlahkan isi array belanja dan berikan hasil penjumalah ke fungsi *callback*
function hitung(belanja, callback) {
    let sum = 0;
    belanja.forEach(function(bl) {
        sum += bl
    })

    callback(sum)
}

// print total dari callback
hitung([100, 200, 150], function(total) {
    console.log(total)
})
```