---
description: Endpoint untuk CRUD Users
---

# Module Users

## Get Users List

<mark style="color:green;">`GET`</mark>`/users`

Endpoint untuk mendapatkan list users

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name     | Type   | Description             |
| -------- | ------ | ----------------------- |
| `name`   | string | Nama dari user          |
| `nik`    | number | NIK User                |
| role\_id | number | Role ID                 |
| page     | number | Halaman keberapa        |
| limit    | number | Jumlah data per halaman |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Found!",
  data: {
    data: [
      {
        id: <int>,
        name: <string>,
        email: <string>,
        nik: <string>,
        last_login: <timestamp>,
        role: {
          id: <int>,
          role_name: <string>
        },
        created_at: <timestamp>,
        updated_at: <timestamp>,
      }
    ],
    pagination: {
      current_page: <int>,
      per_page: <int>,
      total_page: <int>,
      total_data: <int>
    }
  }
}
```
{% endtab %}

{% tab title="401" %}
```json
{
  code: 401,
  status: false,
  message: "Unauthorized",
  data: null,
}
```
{% endtab %}
{% endtabs %}



## Store Users

<mark style="color:green;">`POST`</mark> `/users`

Endpoint untuk menambahkan data users

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name               | Type   | Description                                                                 | Validation                      |
| ------------------ | ------ | --------------------------------------------------------------------------- | ------------------------------- |
| `name`             | string | Nama user                                                                   | required\|string\|max:150       |
| `nik`              | number | NIK user                                                                    | required\|int\|unique           |
| role\_id           | number | Role/Jabatan user                                                           | required\|int\|exists           |
| record\_centre\_id | number | Record Centre yang ditangani jika role petugas record centre                |  nullable\|int                  |
| phone              | number | No HP User                                                                  | required\|int\|max:20           |
| password           | string | Password User                                                               | required\|string\|min:6\|max:30 |
| unit\_pengolah\_id | number | Jika role kepala unit pengolah, maka ini untuk unit pengolah yang ditangani | nullable\|int                   |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 201,
  status: true,
  message: "Sukses menambah data user!",
  data: {
    id: <int>,
    name: <string>,
    email: <string>,
    nik: <string>,
    phone: <string>,
    last_login: <timestamp>,
    role: {
      id: <int>,
      role_name: <string>
    },
    unit_pengolah: {
      id: <int>,
      organization: <string>
    },
    record_centre: {
      id: <int>,
      name: <string>
    },
    created_at: <timestamp>,
    updated_at: <timestamp>,
  },
}
```
{% endtab %}
{% endtabs %}



## Get Detail User

<mark style="color:green;">`GET`</mark>`/users/{id}`

Endpoint untuk mendapatkan informasi detail user

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Found!",
  data: {
    id: <int>,
    name: <string>,
    email: <string>,
    nik: <string>,
    phone: <string>,
    last_login: <timestamp>,
    role: {
      id: <int>,
      role_name: <string>
    },
    unit_pengolah: {
      id: <int>,
      organization: <string>
    },
    record_centre: {
      id: <int>,
      name: <string>
    },
    created_at: <timestamp>,
    updated_at: <timestamp>,
  }
}
```
{% endtab %}
{% endtabs %}



## Edit User

<mark style="color:green;">`PUT`</mark>`/users/{id}`

Endpoint untuk update data user

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name               | Type   | Description                                                                 | Validation                      |
| ------------------ | ------ | --------------------------------------------------------------------------- | ------------------------------- |
| `name`             | string | Nama user                                                                   | required\|string\|max:150       |
| `nik`              | number | NIK user                                                                    | required\|int\|unique           |
| role\_id           | number | Role/Jabatan user                                                           | required\|int\|exists           |
| record\_centre\_id | number | Record Centre yang ditangani jika role petugas record centre                | nullable\|int                   |
| phone              | number | No HP User                                                                  | required\|int\|max:20           |
| password           | string | Password user                                                               | nullable\|string\|min:6\|max:30 |
| unit\_pengolah\_id | number | Jika role kepala unit pengolah, maka ini untuk unit pengolah yang ditangani | nullable\|int                   |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Sukses mengupdate data user!",
  data: {
    id: <int>,
    name: <string>,
    email: <string>,
    nik: <string>,
    phone: <string>,
    last_login: <timestamp>,
    role: {
      id: <int>,
      role_name: <string>
    },
    unit_pengolah: {
      id: <int>,
      organization: <string>
    },
    record_centre: {
      id: <int>,
      name: <string>
    },
    created_at: <timestamp>,
    updated_at: <timestamp>,
  },
}
```
{% endtab %}
{% endtabs %}
