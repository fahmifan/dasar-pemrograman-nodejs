# Looping
Ada beberapa teknik lopping dalam javascript. Yang pertama adalah disebut `for-loop` biasa
```js
for (let step = 0; step < 5; step++) {
  console.log(step + " step to the east");
}
```
Selanjutnya ada built-in function `forEach`
```js
const fruits = ['apple', 'orange', 'tomato', 'cerry']
fruits.forEach(function (fruit) {
    console.log(fruit)
})
```

`forEach` ini melakukan iterasi ke setiap item dalam array. Fungsi ini menerima parameter berupa `fungsi` yang disebut `callback`. `callback` dari `forEach` memiliki parameter pertama yang merupakan item dari setiap iterasi. Jika kita pisah-pisah
```js
// print setiap fruit yang masuk
function print(fruit) {
    console.log(fruit)
}

// iterasi fruits dan jalankan fungsi print di setiap iterasi
fruits.forEach(print)
```