# Mencari arsip dipinjam

<mark style="color:green;">`GET`</mark> `/return-borrows/search-archive`

Endpoint untuk mencari arsip yang sedang dipinjam

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name      | Type   | Description                                    | Validasi |
| --------- | ------ | ---------------------------------------------- | -------- |
| `user_id` | number | Cari berdasarkan user                          | required |
| `keyword` | string | Cari berdasarkan nama/kode arsip yang dipinjam | required |

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
      archive_name: <string>,
      archive_number: <string>,
      clasification_code_id: {
        id: <int>,
        arsip_type: <string>,
        code: <string>,
      },
    }
  ]
}
```
{% endtab %}

{% tab title="400" %}
```json
{
  "error": "Invalid request"
}
```
{% endtab %}
{% endtabs %}
