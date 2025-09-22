# Get Daftar Permintaan Arsip Masuk

<mark style="color:green;">`GET`</mark>`/archives-active/ins`

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name    | Type   | Description                 |
| ------- | ------ | --------------------------- |
| `limit` | number | Filter limitasi per halaman |
| `page`  | number | Filter halaman ke-n         |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Found!",
  data: [
    {
      id: <int>,
      approved_date: <date|null>,
      count_archive: <int>,
      count_revision: <int>,
      user_create: {
        id: <int>,
        name: <string>,
      },
      status: {
        id: <int>,
        archive_in_status: <string>,
      },
      owner_role: {
        id: <int>,
        role_name: <string>
      },
      unit_pengolah: {
        id: <int>,
        code: <string>,
        organization: <string>
      },
    }
  ]
}
```
{% endtab %}
{% endtabs %}
