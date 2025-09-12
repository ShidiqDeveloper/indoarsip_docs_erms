---
description: Module for CRUD master kode kotak
---

# Module Kode Kotak

## Get Kode Kotak

<mark style="color:green;">`GET`</mark>`/box-codes`

Endpoint for get all box codes

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name     | Type   | Description                  |
| -------- | ------ | ---------------------------- |
| `search` | string | Keyword for search some data |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Found!",
  data: [
    {
      id: <int>,
      box_code: <string>,
      length: <int>,
      high_order: <int>,
      back_row_oder: <int>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}

## Store Kode Kotak

<mark style="color:green;">`POST`</mark> `/box-codes`

Endpoint for create new box code

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

{% include "../.gitbook/includes/untitled.md" %}

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 201,
  status: true,
  message: "Sukses menambahkan data kode kotak!",
  data: [
    {
      id: <int>,
      box_code: <string>,
      length: <int>,
      high_order: <int>,
      back_row_oder: <int>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}

## Update Box Codes

<mark style="color:green;">`PUT`</mark>`/box-codes/{id}`

Endpoint for update box code

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name            | Type   | Description           |
| --------------- | ------ | --------------------- |
| `box_code`      | string | Code of box           |
| `length`        | number | Length of box         |
| high\_order     | number | High order of box     |
| back\_row\_oder | number | Back row order of box |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Sukses mengupdate data lokasi box!",
  data: [
    {
      id: <int>,
      box_code: <string>,
      length: <int>,
      high_order: <int>,
      back_row_oder: <int>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}
