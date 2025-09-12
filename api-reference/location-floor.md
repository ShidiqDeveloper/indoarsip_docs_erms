# Location Floor

## Get List Location Floor

<mark style="color:green;">`GET`</mark>`/location-floors`

This endpoint for get all list location floors

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name   | Type   | Description                            |
| ------ | ------ | -------------------------------------- |
| search | string | Keyword for search location floor name |

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
      location_floor: <string>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}

## Store Location Floor

<mark style="color:green;">`POST`</mark> `/location-floors`

This endpoint for store new location floor

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name             | Type   | Description          | Validation                        |
| ---------------- | ------ | -------------------- | --------------------------------- |
| `location_floor` | string | Name of the location | required\|string\|unique\|max:100 |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 201,
  status: true,
  message: "Sukses membuat data lokasi lantai!",
  data: [
    {
      id: <int>,
      location_floor: <string>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}

## Update Location Floors

<mark style="color:green;">`PUT`</mark>`/location-floors/{id}`

This endpoint for update location floor

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name             | Type   | Description       | Validation                        |
| ---------------- | ------ | ----------------- | --------------------------------- |
| `location_floor` | string | Name of location  | required\|string\|unique\|max:100 |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Berhasil mengupdate data lokasi lantai!",
  data: [
    {
      id: <int>,
      location_floor: <string>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}
