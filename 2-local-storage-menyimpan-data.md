Kamu pasti mengalami hal ini saat *login* pada suatu aplikasi misalnya aplikasi Skilvul. Saat kamu melakukan *login* lalu berhasil namun secara sengaja atau tidak sengaja menutup *web browser*  kamu, maka saat kamu mengakses kembali situs web tersebut, kamu tidak akan diminta untuk melakukan *login* kembali bukan? Ini karena data *login* milik kamu sudah disimpan pada *local storage*.

Itulah salah satu penerapan dari *local storage* pada aplikasi web. Dari contoh diatas salah satu fungsi dari *local storage* adalah dapat digunakan untuk menyimpan data secara lokal pada *web browser*.

Kita akan membuat aplikasi web sederhana untuk menyimpan data *login*.

Untuk menyimpan data pada *local storage*, kita menggunakan *method* `setItem()` yang membutuhkan 2 parameter. Parameter pertama adalah *key* yang ingin kita simpan dan parameter kedua adalah data (*value*) dari *key* yang akan disimpan.

Berikut kode yang ada pada *file* `index.html`:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    form div {
      padding: 5px 0px;
    }
  </style>
</head>
<body>
  <form>
    <div>
      <input type="text" id="username" placeholder="username">
    </div>
    <div>
      <input type="password" id="password" placeholder="password">
    </div>
    <div>
      <input type="submit" onclick="login(event)" value="login">
    </div>
  </form>
  <script src="index.js"></script>
</body>
</html>
```
Jika kode di atas dijalankan, maka akan terlihat seperti gambar di bawah ini:
<p style="text-align: center;">
	<img src="https://skilvul-prod.s3-ap-southeast-1.amazonaws.com/lesson/js-intermediate/localstorage-login.png" alt="Console Tab" style="width: 90%;box-shadow: 10px 13px 17px 0px rgba(0,0,0,0.14);-webkit-box-shadow: 10px 13px 17px 0px rgba(0,0,0,0.14);-moz-box-shadow: 10px 13px 17px 0px rgba(0,0,0,0.14);">
</p>

Berikutnya kita akan membuat kode JavaScript pada *file* `index.js`. Jika *user* klik tombol *login*, maka *function* `login()` akan dipanggil dan menjalankan kode di dalamnya. Berikut kode yang ada pada *file* `index.js`:
```js
function login(event) {
  event.preventDefault()

  let username = document.getElementById('username').value;
  localStorage.setItem('username', username); // Simpan data ke Local Storage

  let password = document.getElementById('password').value;
  localStorage.setItem('password', password); // Simpan data ke Local Storage

  window.location.replace("./profile.html") // Redirect ke halaman profile
}
```

Pada contoh dibawah ini kita memasukkan *username* `skilvul` dan *password* `12345` pada *form login* yang diberikan sebelumnya. Maka saat kita klik *button login*, aplikasi akan menyimpan data pada *local storage*. Berikut cara untuk mengecek data yang telah tersimpan pada *local storage* di *web browser*:

1. Klik kanan pada halaman aplikasi web yang sedang diakses. Pilih ***inspect***.
<p style="text-align: center;">
	<img src="https://skilvul-prod.s3-ap-southeast-1.amazonaws.com/lesson/js-intermediate/localstorage-inspect-console.png" alt="Console Tab" style="width: 90%;box-shadow: 10px 13px 17px 0px rgba(0,0,0,0.14);-webkit-box-shadow: 10px 13px 17px 0px rgba(0,0,0,0.14);-moz-box-shadow: 10px 13px 17px 0px rgba(0,0,0,0.14);">
</p>

2. Pilih dan klik ***Application***. Lalu klik ***Local Storage*** di sisi *tab* sebelah kiri.
<p style="text-align: center;">
	<img src="https://skilvul-prod.s3-ap-southeast-1.amazonaws.com/lesson/js-intermediate/localstorage-console.png" alt="Console Tab" style="width: 90%;box-shadow: 10px 13px 17px 0px rgba(0,0,0,0.14);-webkit-box-shadow: 10px 13px 17px 0px rgba(0,0,0,0.14);-moz-box-shadow: 10px 13px 17px 0px rgba(0,0,0,0.14);">
</p>