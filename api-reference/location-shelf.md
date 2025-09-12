# Location Shelf

## Get Location Shelf

<mark style="color:green;">`GET`</mark>`/location-shelf`

Endpoint for get list location shelf

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name     | Type   | Description                 |
| -------- | ------ | --------------------------- |
| `search` | string | Keyword for search location |

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
      location_shelf: <string>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}

## Store Location Shelf

<mark style="color:green;">`POST`</mark> `/location-shelf`

Endpoint for create new location

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name             | Type   | Description          | Validation                        |
| ---------------- | ------ | -------------------- | --------------------------------- |
| `location_shelf` | string | Name of the location | required\|string\|unique\|max:100 |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 201,
  status: true,
  message: "Berhasil menambahkan data lokasi shelf!",
  data: [
    {
      id: <int>,
      location_shelf: <string>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}

## Update Location Shelf

<mark style="color:green;">`POST`</mark> `/location-shelf/{id}`

Endpoint for update location shelf

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name             | Type   | Description          | Validation                        |
| ---------------- | ------ | -------------------- | --------------------------------- |
| `location_shelf` | string | Name of the location | required\|string\|unique\|max:100 |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Berhasil mengupdate data lokasi shelf!",
  data: [
    {
      id: <int>,
      location_shelf: <string>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}
