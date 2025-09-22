# Mendapatkan list tunjuk silang arsip

<mark style="color:green;">`GET`</mark>`/archive-relations`

Endpoint untuk mendapatkan list tunjuk silang arsip

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name      | Type   | Description                                                                                 |
| --------- | ------ | ------------------------------------------------------------------------------------------- |
| page      | number | Filter halaman ke-n                                                                         |
| `keyword` | string | Filter berdasarkan nama arsip utama, kode arsip utama, nama arsip relasi, kode arsip relasi |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  status: true,
  status_code: 200,
  message: "Found!",
  data: [
    {
      relation_type: {
        id: <int>,
        relation_type: <string>,
      },
      archive: {
        id: <int>,
        archive_name: <string>,
        archive_code: <string>,
      },
      archive_relation: {
        id: <int>,
        archive_name: <string>,
        archive_code: <string>,
      },
      note: <string>,
      created_at: <timestamp>,
      updated_at: <timestamp>
    }
  ]
}
```
{% endtab %}
{% endtabs %}
