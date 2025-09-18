# Get Data

<mark style="color:green;">`GET`</mark>`/archive-units`

Endpoint untuk mendapatkan list unit kearsipan beserta orang nya

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name    | Type   | Description                  |
| ------- | ------ | ---------------------------- |
| `limit` | number | Limitasi per halaman         |
| `page`  | number | Menuju halaman ke-n          |
| keyword | string | Filter berdasarkan nama/kode |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  status_code: 200,
  status: true,
  message: "Found",
  data: {
    data: [
      {
        id: <int>,
        unit_name: <string>,
        unit_code: <string>,
        users: [
          {
            name: <string>,
            role: {
              id: <int>,
              role_name: <string>
            },
            unit_pengolah: {
              id: <int>,
              organization: <string>
            },
          }
        ],
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
{% endtabs %}
