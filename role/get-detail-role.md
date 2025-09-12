---
description: Ednpoint untuk mendapatkan detail role
---

# Get Detail Role

<mark style="color:green;">`GET`</mark>`/roles/{id_role}`

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
    id: <int>,
    role_name: <string>,
    scope: <string>,
    unit_work: {
      id: <int>,
      code: <string>,
      organization: <string>,
    }
    created_at: <timestamp>,
    updated_at: <timestamp>,
  },
}
```
{% endtab %}
{% endtabs %}
