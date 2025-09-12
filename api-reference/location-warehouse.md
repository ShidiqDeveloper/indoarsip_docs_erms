# Location Warehouse

## Get List Location Warehouses

<mark style="color:green;">`GET`</mark>`/location-warehouses`

This endpoint for get all list location warehouse

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name   | Type   | Description                                |
| ------ | ------ | ------------------------------------------ |
| search | string | Keyword for search location warehouse name |

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
      location_warehouse: <string>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}

## Store Location Warehouse

<mark style="color:green;">`POST`</mark> `/location-warehouses`

This endpoint for store new location warehouse

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name                 | Type   | Description          | Validation                        |
| -------------------- | ------ | -------------------- | --------------------------------- |
| `location_warehouse` | string | Name of the location | required\|string\|unique\|max:100 |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 201,
  status: true,
  message: "Berhasil menambahkan data lokasi gudang!",
  data: [
    {
      id: <int>,
      location_warehouse: <string>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}

## Update Location Warehouse

<mark style="color:green;">`PUT`</mark>`/location-warehouses/{id}`

This endpoint for update location warehouse

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name                 | Type   | Description                | Validation                        |
| -------------------- | ------ | -------------------------- | --------------------------------- |
| `location_warehouse` | string | Name of location warehouse | required\|string\|unique\|max:100 |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Berhasil mengupdate data lokasi gudang!",
  data: [
    {
      id: <int>,
      location_warehouse: <string>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}
