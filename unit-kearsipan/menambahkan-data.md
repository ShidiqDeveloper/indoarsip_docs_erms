# Menambahkan Data

<mark style="color:green;">`POST`</mark> `/archive-units`

Endpoint untuk menambahkan data unit kearsipan

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
  users: [<int>, ...<int>]
}
```

| Name        | Type   | Description              | Validation                       |
| ----------- | ------ | ------------------------ | -------------------------------- |
| `unit_name` | string | Nama unit kearsipan      | required\|string\|max:255        |
| `unit_code` | string | Kode unit kearsipan      | required\|string\|max:50         |
| users       | array  | User id penanggung jawab | required\|array\|exists:users.id |

**Response**

{% tabs %}
{% tab title="201" %}
```json
{
  status_code: 201,
  status: true,
  message: "Sukses menambah unit kearsipan!",
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
