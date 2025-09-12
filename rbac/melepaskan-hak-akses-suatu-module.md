---
description: Endpoint ini untuk melepaskan hak akses suatu module untuk role tertentu
---

# Melepaskan Hak Akses Suatu Module

<mark style="color:green;">`PUT`</mark> `/roles/{role_id}/modules/{id_module}/ungranted`

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
  message: "Berhasil membatalkan hak akses!",
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
