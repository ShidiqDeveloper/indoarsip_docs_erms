# Autentikasi

Autentikasi menggunakan metode JWT (JSON Web Token). Setiap request yang membutuhkan authentikasi, maka wajib menyertakan di header nya berupa

Authorization: Bearer {Token}

Response gagal di semua API yang membutuhkan authentikasi

```
{
  code: 401,
  status: false,
  message: "Unauthorized",
  data: null,
}
```
