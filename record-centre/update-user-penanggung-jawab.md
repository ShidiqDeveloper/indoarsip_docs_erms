# Update User Penanggung Jawab

<mark style="color:green;">`PUT`</mark>`/record-centres/{id_unit}/change-users`

Endpoint untuk mengubah list user penanggung jawab

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

```
{
  users: [<int>, ...<int>]
}
```

| Name    | Type  | Description                | Validation                       |
| ------- | ----- | -------------------------- | -------------------------------- |
| `users` | array | List user penanggung jawab | required\|array\|exists:users.id |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  status_code: 200,
  status: true,
  message: "Sukses mengubah penanggung jawab record centre!",
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
