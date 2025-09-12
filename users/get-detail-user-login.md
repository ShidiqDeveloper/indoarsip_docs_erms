---
description: Mendapatkan detail user yang sedang login
---

# Get Detail User Login

<mark style="color:green;">`GET`</mark> `/profile`

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
  status: true,
  message: "Found!",
  data: {
    data: [
      {
        id: <int>,
        name: <string>,
        email: <string>,
        role: {
          id: <int>,
          role_name: <string>
        },
        unit_pengolah: {
          id: <int>,
          organization: <string>
        } // NULL,
        record_centre: {
          id: <int>,
          name: <string>
        } // NULL,
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
  }
}
```
{% endtab %}
{% endtabs %}
