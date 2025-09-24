# Get Detail Peminjaman Arsip

<mark style="color:green;">`GET`</mark>`/borrow-requests/{id_borrow}`

Endpoint untuk mendapatkan detail permintaan peminjaman arsip

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
  status: true,
  status_code: 200,
  message: "Found!",
  data: {
    id: <id>,
    borrow_request_number: <string>,
    borrow_date: <date>,
    borror_return_date: <date>,
    borrow_reason: <string>,
    file_attachment: <string|null>,
    workflow_reject_reason: <string|null>,
    user_borrow: {
      id: <int>,
      name: <string>,
    },
    workflow_status: {
      id: <int>,
      status_name: <string>,
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
        borrow_status: {
          id: <int>,
          status: <string>
        },
        storage_location: {
          id: <int>,
          location_name: <string>,
        },
      }
    ]
    created_at: <timestamp>,
    updated_at: <timestamp>
  }
}
```
{% endtab %}
{% endtabs %}
