---
description: This Endpoint for crud location acrhive
---

# Moduel Location

## Get location

<mark style="color:green;">`GET`</mark>`/location-archives`

Get list location archive

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Response**

{% tabs %}
{% tab title="200 (Archive Exists)" %}
```json
{
  code: 200,
  status: true,
  message: "Found!",
  data: [
    {
      id: <int>,
      location_name: <string>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
      folders: [
        {
          id: <int>,
          location_name: <string>,
          created_at: <timestamp>,
          updated_at: <timestamp>,
        }
      ],
      archives: [
        {
          id: <int>,
          archive_name: <string>,
          created_at: <timestamp>,
          updated_at: <timestamp>,
        }
      ]
    }
  ]
}
```
{% endtab %}

{% tab title="200 (Archive Empty)" %}
```
{
  code: 200,
  status: true,
  message: "Found!",
  data: [
    {
      id: <int>,
      location_name: <string>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
      folders: [
        {
          id: <int>,
          location_name: <string>,
          created_at: <timestamp>,
          updated_at: <timestamp>,
        }
      ],
      archives: []
    }
  ]
}
```
{% endtab %}
{% endtabs %}



## Store Location / Generate Location

<mark style="color:green;">`POST`</mark> `/location-archives`

This endpoint for generate location archive

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name                    | Type   | Description                            |
| ----------------------- | ------ | -------------------------------------- |
| `warehouse_location_id` | number | ID From master data location warehouse |
| `floor_location_id`     | number | ID from master data floor location     |
| location\_baris         | string | String input                           |
| location\_shelf         | string | String Input                           |
| shelf\_location\_id     | number | ID from master data location shelf     |
| box\_code\_id           | number | ID from master data box code           |

**Response**

{% tabs %}
{% tab title="201" %}
```json
{
  code: 201,
  status: true,
  message: "Berhasil generate lokasi arsip!",
  data: []
}
```
{% endtab %}
{% endtabs %}
