---
description: >-
  Mendapatkan semua list module yang ada dan memberi tanda suatu modul telah
  diberikan hak akses/tidak
---

# List Module Pada Suatu Role

<mark style="color:green;">`GET`</mark> `/`roles/{role\_id}/modules

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name            | Type   | Description                                         |
| --------------- | ------ | --------------------------------------------------- |
| `parent_module` | number | Filter untuk get list module berdasarkan parent nya |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: false,
  message: "Found!",
  data: [
    {
      id: <int>,
      module_name: <string>,
      module_description: <string>,
      childs: [
        {
          id: <int>,
          module_name: <string>,
          module_description: <string>,
          created_at: <timestamp>,
          updated_at: <timestamp>,
          granted: <bool>
        }
      ]
    }
  ],
}
```
{% endtab %}
{% endtabs %}
