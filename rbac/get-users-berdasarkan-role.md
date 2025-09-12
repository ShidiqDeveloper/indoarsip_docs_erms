---
description: Mendapatkan semua list users berdasarkan role tertentu
---

# Get Users Berdasarkan Role

<mark style="color:green;">`GET`</mark> `/`roles/{role\_id}/users

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name      | Type   | Description                                 |
| --------- | ------ | ------------------------------------------- |
| `keyword` | string | Filter user berdasarkan nama, email & no HP |

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
      name: <string>,
      email: <string>,
      phone: <string>,
      created_at: <timestamp>,
      updated_at: <timestamp>
    }
  ]
}
```
{% endtab %}
{% endtabs %}
