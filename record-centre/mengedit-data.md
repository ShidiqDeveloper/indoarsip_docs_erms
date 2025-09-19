# Mengedit Data

<mark style="color:green;">`PUT`</mark>`/record-centres/{id_rc}`

Endpoint untuk mengedit data record centre

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

```
{
  name: <string>
}
```

| Name        | Type   | Description         | Validation                |
| ----------- | ------ | ------------------- | ------------------------- |
| `unit_name` | string | Nama unit kearsipan | required\|string\|max:255 |

**Response**

{% tabs %}
{% tab title="201" %}
```json
{
  status_code: 200,
  status: true,
  message: "Sukses mengedit record centre!",
  data: {
    id: <int>,
    name: <string>,
    rc_level: <int>,
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
  },
}
```
{% endtab %}
{% endtabs %}
