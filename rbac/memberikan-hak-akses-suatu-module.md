---
description: Endpoint ini untuk memberikan akses suatu module untuk role tertentu
---

# Memberikan Hak Akses Suatu Module

<mark style="color:green;">`PUT`</mark> `/`roles/{role\_id}/modules/{id\_module}/granted

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
  code: 200,
  status: false,
  message: "Berhasil memberikan hak akses!",
  data: [
    {
      id: <int>,
      module_name: <string>,
      module_description: <string>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
      granted: <bool>
    }
  ],
}
```
{% endtab %}
{% endtabs %}
