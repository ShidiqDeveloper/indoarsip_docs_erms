# Module Clasification Code

## Get clasification code

<mark style="color:green;">`GET`</mark>`/clasification-codes`

Get all clasficiation code

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name     | Type   | Description                         |
| -------- | ------ | ----------------------------------- |
| `search` | string | Search data for arsip type and code |

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
      arsip_type: <string>,
      code: <string>,
      duration_active_year: <string>,
      duration_inactive_year: <string>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}



## Store clasification code

<mark style="color:green;">`POST`</mark> `/clasification-codes`

Store new data clasification code

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name                     | Type   | Description                       | Validation                        |
| ------------------------ | ------ | --------------------------------- | --------------------------------- |
| `arsip_type`             | string | Arsip type                        | required\|string\|max:255         |
| `code`                   | string | Code                              | required\|string\|max:255\|unique |
| duration\_activve\_year  | number | Duration active archive in year   | required\|number\|min:1           |
| duration\_inactive\_year | number | Duration inactive archive in year | required\|number\|min:1           |

**Response**

{% tabs %}
{% tab title="201" %}
```json
{
  code: 201,
  status: true,
  message: "Berhasil menambahkan data kode klasifikasi!",
  data: {
    id: <int>,
    arsip_type: <string>,
    code: <string>,
    duration_active_year: <string>,
    duration_inactive_year: <string>,
    created_at: <timestamp>,
    updated_at: <timestamp>,
  }
}
```
{% endtab %}
{% endtabs %}



## Update clasification code

<mark style="color:green;">`PUT`</mark>`/clasification-codes/{id}`

Update data clasification code

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name                     | Type   | Description                       | Validation                        |
| ------------------------ | ------ | --------------------------------- | --------------------------------- |
| `arsip_type`             | string | Arsip type                        | required\|string\|max:255         |
| `code`                   | string | Code                              | required\|string\|max:255\|unique |
| duration\_activve\_year  | number | Duration active archive in year   | required\|number\|min:1           |
| duration\_inactive\_year | number | Duration inactive archive in year | required\|number\|min:1           |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Berhasil mengupdate data kode klasifikasi!",
  data: {
    id: <int>,
    arsip_type: <string>,
    code: <string>,
    duration_active_year: <string>,
    duration_inactive_year: <string>,
    created_at: <timestamp>,
    updated_at: <timestamp>,
  }
}
```
{% endtab %}
{% endtabs %}
