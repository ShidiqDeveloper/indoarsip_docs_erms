---
description: Endpoint ini untuk menambah data role baru
---

# Menambah Role

<mark style="color:green;">`POST`</mark> `/roles`

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name           | Type   | Description                 | Validation                                  |
| -------------- | ------ | --------------------------- | ------------------------------------------- |
| role\_name     | string | Nama role                   | required\|string\|max:100\|unique           |
| unit\_work\_id | number | Bagian dari unit kerja mana | required\|in\|exists:organization\_units.id |
| scope          | string | Bagian darimana kah role in | required\|string\|max:50                    |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 201,
  status: true,
  message: "Sukses menambah data role!",
  data: {
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
  },
}
```
{% endtab %}
{% endtabs %}
