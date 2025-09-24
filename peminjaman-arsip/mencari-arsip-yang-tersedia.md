# Mencari Arsip Yang Tersedia

<mark style="color:green;">`GET`</mark>`/borrow-requests/search-archives`

Endpoint untuk mencari arsip aktif yang status nya tersedia

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name      | Type   | Description                                                |
| --------- | ------ | ---------------------------------------------------------- |
| `keyword` | string | Cari berdasarkan nama arsip, nomor arsip, kode klasifikasi |

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
      storage_location: {
        id: <int>,
        location_name: <string>,
      },
    }
  ]
}
```
{% endtab %}
{% endtabs %}
