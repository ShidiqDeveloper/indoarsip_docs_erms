# Menambahkan Data

<mark style="color:green;">`POST`</mark> `/record-centres`

Endpoint untuk menambahkan data record centre. Setiap penambahan RC rc\_level auto set isi 2

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

```
{
  name: <string>,
  users: [<int>, ...<int>]
}
```

| Name        | Type   | Description              | Validation                       |
| ----------- | ------ | ------------------------ | -------------------------------- |
| `unit_name` | string | Nama unit kearsipan      | required\|string\|max:255        |
| users       | array  | User id penanggung jawab | required\|array\|exists:users.id |

**Response**

{% tabs %}
{% tab title="201" %}
```json
{
  status_code: 201,
  status: true,
  message: "Sukses menambah record centre!",
  data: {
    id: <int>,
    name: <string>,
    rc_level: <string>,
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
