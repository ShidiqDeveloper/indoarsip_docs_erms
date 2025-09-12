---
description: Endpoint untuk mendapatkan list role yang sudah tersedia
---

# Get List Role

<mark style="color:green;">`GET`</mark>`/roles`

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name       | Type   | Description                     |
| ---------- | ------ | ------------------------------- |
| role\_name | string | Filter berdasarkan nama role    |
| limit      | number | Limitasi per halaman            |
| page       | number | Filter menuju halaman ke berapa |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Found",
  data: {
    data: [
      {
        id: <int>,
        role_name: <string>,
        scope: <string>,
        unit_work: {
          id: <int>,
          code: <string>,
          organization: <string>
        },
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
