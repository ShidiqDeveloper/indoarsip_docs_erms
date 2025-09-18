# Mencari Users

<mark style="color:green;">`GET`</mark>`/users/search`

Endpoint untuk mencari list users

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name               | Type   | Description                              |
| ------------------ | ------ | ---------------------------------------- |
| `keyword`          | string | Mencari berdasarkan nama/nik/email/phone |
| `unit_pengolah_id` | number | Filter berdasarkan organisasi            |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  status_code: 200,
  status: true,
  message: "Found!",
  data: [
    {
      id: <int>,
      name: <string>,
      email: <string>,
      nik: <string>,
      role: {
        id: <int>,
        role_name: <string>
      },
      unit_pengolah: {
        id: <int>,
        organization: <string>
      },
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ],
}
```
{% endtab %}
{% endtabs %}
