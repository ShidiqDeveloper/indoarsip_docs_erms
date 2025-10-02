# Get Detail Pengembalian Arsip

<mark style="color:green;">`GET`</mark> `/return-borrows/{id_return}`

Endpoint untuk mendapatkan detail permintaan pengembalian arsip

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
  message: "Ditemukan!",
  data: {
    id: <int>,
    return_number: <string>,
    return_date: <date>,
    return_note: <string|null>,
    reject_reason: <string|null>,
    workflow_status: {
      id: <int>,
      status_name: <string>,
    },
    borrow_request: {
      borrow_request_number: <string>,
      borrow_date: <date>,
      borror_return_date: <date>,
      borrow_reason: <string>,
    },
    user_borrow: {
      id: <int>,
      name: <string>,
    },
    organization: {
      id: <int>,
      code: <int>,
      name: <string>,
    },
    archives: [
      {
        id: <int>,
        archive_name: <string>,
        archive_code: <string>,
        clasification_code_id: {
          id: <int>,
          arsip_type: <string>,
          code: <string>,
        },
        unit_pengolah: {
          id: <int>,
          code: <string>,
          organization: <string>
        },
      }
    ]
  }
}
```
{% endtab %}
{% endtabs %}
