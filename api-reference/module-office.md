---
description: Endpoint untuk melakukan CRUD pada data offices
---

# Module Office

## Get Data

<mark style="color:green;">`GET`</mark>`/`offices

Mendapatkan data offices

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name          | Type   | Description                  |
| ------------- | ------ | ---------------------------- |
| `office_name` | string | Nama Office                  |
| `limit`       | number | Limitasi per page            |
| page          | number | informasi menuju halaman ke- |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Found",
  data: {
    data: [
      {
        id: <int>,
        office_name: <string>,
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
  },
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





## Store

<mark style="color:green;">`POST`</mark> `/offices`

Menambahkan data office

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name          | Type   | Description | Validation                        |
| ------------- | ------ | ----------- | --------------------------------- |
| `office_name` | string | Nama Office | required\|string\|max:100\|unique |

**Response**

{% tabs %}
{% tab title="201" %}
```json
{
  code: 201,
  status: true,
  message: "Sukses menambah data office!",
  data: null,
}
```
{% endtab %}
{% endtabs %}



## Get Detail Office

<mark style="color:green;">`GET`</mark>`/offices/{id}`

Endpoint untuk mendapatkan detail data office

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
    office_name: <string>,
    created_at: <timestamp>,
    updated_at: <timestamp>,
  },
}
```
{% endtab %}

{% tab title="404" %}
```json
{
  code: 404,
  status: false,
  message: "Data tidak ditemukan!",
  data: null,
}
```
{% endtab %}
{% endtabs %}



## Edit Office

<mark style="color:green;">`PUT`</mark>`/offices/{id}`

Endpoint untuk mengupdate data office

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name          | Type   | Description | Validation                        |
| ------------- | ------ | ----------- | --------------------------------- |
| `office_name` | string | Nama office | required\|string\|max:100\|unique |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Sukses mengupdate data office!",
  data: {
    id: <int>,
    office_name: <string>,
    created_at: <timestamp>,
    updated_at: <timestamp>,
  },
}
```
{% endtab %}

{% tab title="400" %}
```json
{
  code: 400,
  status: false,
  message: "Validation Error!",
  data: [
    {
      field: <string>,
      message: <string>
    }
  ],
}
```
{% endtab %}
{% endtabs %}
