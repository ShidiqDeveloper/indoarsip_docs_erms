# Mengedit Data

<mark style="color:green;">`PUT`</mark>`/archive-units/{id_unit}`

Endpoint untuk mengedit data unit kearsipan

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

```
{
  unit_name: <string>,
  unit_code: <string>,
}
```

| Name        | Type   | Description         | Validation                |
| ----------- | ------ | ------------------- | ------------------------- |
| `unit_name` | string | Nama unit kearsipan | required\|string\|max:255 |
| `unit_code` | string | Kode unit kearsipan | required\|string\|max:50  |

**Response**

{% tabs %}
{% tab title="201" %}
```json
{
  status_code: 200,
  status: true,
  message: "Sukses mengedit unit kearsipan!",
  data: {
    id: <int>,
    unit_name: <string>,
    unit_code: <string>,
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
