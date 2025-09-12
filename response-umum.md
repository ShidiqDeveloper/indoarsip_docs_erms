---
description: >-
  Pada bagian ini menampilkan informasi response yang umum digunakan dari
  berbagai endpoint API
---

# Response Umum

Response Created / OK

```
{
  code: 200 / 201,
  status: true,
  message: <string>,
  data: null,
}
```

Response Error Validasi

```
{
  code: 400,
  status: false,
  message: <string>,
  data: [
    {
      field: <string>,
      message: <string>
    }
  ],
}
```

Response Data TIdak Ditemukan

```
{
  code: 404,
  status: false,
  message: <string>,
  data: null,
}
```

Response Error Server

```
{
  code: 500,
  status: false,
  message: <string>,
  data: null,
}
```
