Pada topik sebelumnya kamu telah mempelajari cara menyimpan data pada *local storage* menggunakan `setItem()`. Pada topik ini kita akan melanjutkan pembahasan bagaimana mengambil data yang telah tersimpan pada *local storage* .

Untuk mengambil data yang telah tersimpan pada *local storage*, kita dapat menggunakan *method* `getItem()` yang membutuhkan 1 parameter. Parameter tersebut adalah *key* dari data yang kita inginkan.

Untuk lebih memahami, kita akan melanjutkan aplikasi yang telah dibuat pada topik sebelumnya yaitu aplikasi yang dapat digunakan untuk *login* dan menampilkan data profil *user* yang telah berhasil *login*. Kita akan membuat tampilan profil pada *file* bernama `profile.html`.

Berikut detail kode yang ada pada *file* `profile.html`:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body onload="user()">

  <h1>Profile</h1>
  <div id="username"></div>
  <button type="submit" onclick="logout()">logout</button>

  <script src="profile.js"></script>
</body>
</html>
```

Selanjutnya kita akan membuat *function* `user()` yang digunakan untuk mengambil data pada *local storage*. Kita akan menggunakan *method* `getItem()` untuk menampilkan data `username` pada halaman `profile.html`. Jika user berhasil *login* maka akan diarahkan ke halaman `profile.html` yang menampilkan data `username`. Data tersebut didapatkan dari data yang telah disimpan pada *local storage*. Kita juga akan membuat *function* `logout()` yang nantinya dapat digunakan jika *user* ingin keluar dari *login session*. Berikut ini detail kode pada *file* `profile.js`. 

```js
function user() {
  let username = localStorage.getItem('username'); // Mengambil data dari Local Storage
  document.getElementById('username').innerHTML = `<p> ${username} </p>`;
}

function logout() {
  // Menghapus data dari Local Storage
  localStorage.removeItem("username");
  localStorage.removeItem("password");
  window.location.replace('./index.html');
}
```
Jika kita telah berhasil mengakses halaman `profile.html` maka tampilan pada halaman tersebut akan menjadi seperti ini:

<p style="text-align: center;">
	<img src="https://skilvul-prod.s3-ap-southeast-1.amazonaws.com/lesson/js-intermediate/localstorage-getitem-profile.png" alt="Console Tab" style="width: 90%;box-shadow: 10px 13px 17px 0px rgba(0,0,0,0.14);-webkit-box-shadow: 10px 13px 17px 0px rgba(0,0,0,0.14);-moz-box-shadow: 10px 13px 17px 0px rgba(0,0,0,0.14);">
</p>