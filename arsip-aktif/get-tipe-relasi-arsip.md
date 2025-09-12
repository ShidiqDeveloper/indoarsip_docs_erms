---
description: Endpoint untuk mengambil list tipe relasi arsip
---

# Get Tipe Relasi Arsip

<mark style="color:green;">`GET`</mark> `/archive-relations`

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  status: true,
  status_code: 200,
  message: 'Found!',
  data: [
    {
      id: <int>,
      relation_type: <string>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}
