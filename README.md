# Final-Project-Katalon-API-Testing
Final Project for Automated Testing with Katalon Studio in BTDP 2022 with Hacktiv8 as Learning Partner

## Informasi Dasar
Aplikasi API Testing (Reqres) adalah sebuah Final Project dari `BFI Technology Development Program (BTDP) feat Hactiv8` dengan topik `Automated Testing with Katalon`, aplikasi ini terfokus pada bagaimana cara kerja API dengan melakukan testing pada semua end Point API, yang dibuat oleh

Nama		                 : `Arrifqi Aziz Ardhiansyah`\
Kode Peserta             : `KSAT006ONL009`\
Dokumentasi setiap Sesi  : [`Repository Bootcamp`](https://github.com/arrifqiaziz/BTDP-Hacktiv8-2022)\
Final Project Website    : [`Repository FP Website`](https://github.com/arrifqiaziz/Final-Project-Katalon-Website-Testing)\
Final Project Mobile     : [`Repository FP Mobile`](https://github.com/arrifqiaziz/Final-Project-Katalon-Mobile-Testing)\
Final Project API        : [`Repository DP API`](https://github.com/arrifqiaziz/Final-Project-Katalon-API-Testing)

---

# Panduan Penggunaan Aplikasi

## Requirement yang harus disipkan sebelum running aplikasi ini adalah :
- Menggunakan `Bahasa Groovy` based `Katalon Studio versi 8.3.5`
- Testing dilakukan pada End-Point API yang disediakan oleh [`Reqres`](https://reqres.in/)
- Testing dilaksanakan dengan Website Browser `Google Chrome versi 103.0.5060.114`

## Document Test Plan
Sebelum pelaksanaan testing, dibuat dokumen Test Plan dan Test Plan Scenario untuk mendokumentasikan perubahan testing dan pedoman dalam melakukan testing\
Yang dapat dilihat di [Document Test Plan](https://github.com/arrifqiaziz/Final-Project-Katalon-API-Testing/tree/main/Test%20Plan)

## Ringkasan Hasil Testing
Pada pelaksanaan testing dilakukan testing pada `37 Test Case` dengan hasil :
```
37 Passed
0 Failed
0 Not Executed
```
Sehingga hasil pengujian adalah `100% Passed`

## IF ELSE Condition
Pada testing ini juga dimasukan satu test case yang berisi `IF ELSE CONDITION`, yaitu pada `Test Case Get User by ID 12345 Not Found`
```
if (Response_Code==404) {
    WS.verifyResponseStatusCode(Response, 404)
} else {
    WS.verifyResponseStatusCode(Response, 200)
}
```
Dimana, jika hasil response code adalah 404, akan masuk ke verify response 404, jika tidak akan masuk pada verify response 200

## Report
Pada pengujian, jika harus satu-satu test case di test akan memakan waktu lama, sehingga dibuat `Test Suite` agar dapat menjalankan beberapa test case secara bersamaan yaitu
```
TS Get Resurces
TS Get User per Page
TS Get User by ID
TS Post, Put and Delete User
TS Register and Login
```
Untuk lebih memudahkan pengujian dibuat `Test Suites Collection` agar dapat menjalankan beberapa Test Suites secara bersamaan yaitu
```
TST Test All
```
Dan ketika selesai testing, hasil pengujian di Export kedalam bentuk PDF dan HTML adar dapat dilihat lebih rapih di [Report](https://github.com/arrifqiaziz/Final-Project-Katalon-API-Testing/tree/main/Report)

## Screenshot
Screenshot Testing hasil testing tidak dimasukan kedalam readme agar rapih\
Jika ingin melihat screenshot silahkan klik di [Screenshot Testing](https://github.com/arrifqiaziz/Final-Project-Katalon-API-Testing/tree/main/Screenshot)

# End Point
Keseluruhan Endpoint pada Reqress diuji pada project ini adalah :

## GET User by Page
Untuk mendapatkan data user berdasarkan halaman, yang mana pada Reqress disediakan 2 halaman\
Akan menghasilkan response code `200 OK` dan result user
```
https://reqres.in/api/users?page=1
https://reqres.in/api/users?page=2
```

## GET User by ID
Untuk mendapatkan data single user berdasarkan ID, yang mana pada Reqress disediakan 12 ID\
Akan menghasilkan response code `200 OK` dan result user yang dimaksud
```
https://reqres.in/api/users/?id=1
https://reqres.in/api/users/?id=2
https://reqres.in/api/users/?id=3
https://reqres.in/api/users/?id=4
https://reqres.in/api/users/?id=5
https://reqres.in/api/users/?id=6
https://reqres.in/api/users/?id=7
https://reqres.in/api/users/?id=8
https://reqres.in/api/users/?id=9
https://reqres.in/api/users/?id=10
https://reqres.in/api/users/?id=11
https://reqres.in/api/users/?id=12
```
Jika request id yang tidak ada maka akan menghasilkan response code `404 NOT FOUND` dan tidak ada result
```
https://reqres.in/api/users/?id=12345
```
Jika request id dengan delay maka menambahkan delay\
Akan menghasilkan response code `200 OK` dan result user yang dimaksud dengan jeda 3 detik (dapat diubah sesuai keinginan)
```
https://reqres.in/api/users?page=1&delay=3
```

## POST User
```
https://reqres.in/api/users
```
Untuk menambahkan data user, dengan memasukan pada `HTTP BODY` dengan atribut `TEXT` dan `JSON`\
Akan menghasilkan response code `201 CREATED` dan hasil penambahan data
```
{
    "name": "arrifqi",
    "job": "leader"
}
```

## PUT User
Untuk mengubah data user berdasar id nya semisal mengubah data pada id 7\
```
https://reqres.in/api/users/7
```
Lalu dengan memasukan pada `HTTP BODY` dengan atribut `TEXT` dan `JSON`\
Akan menghasilkan response code `200 OK` dan hasil perubahan data
```
{
    "name": "kikiw",
    "job": "president"
}
```

## DELETE User
Untuk mengubah data user berdasar id nya semisal mengubah data pada id 5\
```
https://reqres.in/api/users/5
```
Akan menghasilkan response code `204 NO CONTECT` dan tanpa result, karena sudah dihapus

### GET Resources
```
https://reqres.in/api/unknown
```
Untuk mendapatkan data resources berdasarkan ID, yang mana pada Reqress disediakan 12 ID\
Akan menghasilkan response code `200 OK` dan result resources yang dimaksud
```
https://reqres.in/api/unknown?id=1
https://reqres.in/api/unknown?id=2
https://reqres.in/api/unknown?id=3
https://reqres.in/api/unknown?id=4
https://reqres.in/api/unknown?id=5
https://reqres.in/api/unknown?id=6
https://reqres.in/api/unknown?id=7
https://reqres.in/api/unknown?id=8
https://reqres.in/api/unknown?id=9
https://reqres.in/api/unknown?id=10
https://reqres.in/api/unknown?id=11
https://reqres.in/api/unknown?id=12
```
Jika request id yang tidak ada maka akan menghasilkan response code `404 NOT FOUND` dan tidak ada result
```
https://reqres.in/api/unknown?id=12345
```
## POST Register
```
https://reqres.in/api/register
```
Untuk dapat register, harus dengan memasukan data user yang sudah disediakan oleh Reqres\
Lalu masukan data pada `HTTP BODY` dengan atribut `TEXT` dan `JSON`
```
{
    "email": "eve.holt@reqres.in",
    "password": "cityslicka"
}
```
Akan menghasilkan response code `200 OK` dan `TOKEN`\
Result Register Success
```
{
  "id":4,
  "token":"QpwL5tke4Pnpja7X4"
}
```
Jika memasukan data yang tidak disediakan, maka akan menghasilkan response code `400 BAD REQUEST`
Result Register Failed\
```
{
  "error":"Note: Only defined users succeed registration"
}
```

## POST Login
```
https://reqres.in/api/login
```
Untuk dapat login, harus dengan memasukan data user yang sudah disediakan oleh Reqres\
Lalu masukan data pada `HTTP BODY` dengan atribut `TEXT` dan `JSON`\
```
{
    "email": "eve.holt@reqres.in",
    "password": "cityslicka"
}
```
Akan menghasilkan response code `200 OK` dan `TOKEN`\
Result Login Success
```
{
  "token":"QpwL5tke4Pnpja7X4"
}
```
Jika memasukan data yang tidak disediakan, maka akan menghasilkan response code `400 BAD REQUEST`\
Result Login Failed
```
{
  "error":"user not found"
}
```

# Signature
Made with Heart, Hard Work, Smart Think and Whole Soul <3

Name  : Arrifqi Aziz Ardhiansyah\
Participant Code Java Springboot  : JVSB001ONL009\
Participant Code Katalon : KSAT006ONL009


[LinkedIn](https://www.linkedin.com/in/arrifqiaziz/) | [GitHub](https://github.com/arrifqiaziz)
