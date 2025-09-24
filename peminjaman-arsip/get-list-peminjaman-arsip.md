# Get List Peminjaman Arsip

<mark style="color:green;">`GET`</mark>`/borrow-requests`

Endpoint untuk mendapatkan list daftar permintaan arsip yang dipinjam

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name                 | Type   | Description                                |
| -------------------- | ------ | ------------------------------------------ |
| `keyword`            | string | Filter berdasarkan nomor request/ peminjam |
| `page`               | number | Filter halaman ke-n                        |
| workflow\_status\_id | number | Filter berdasarkan status workflow         |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  status: true,
  status_code: 200,
  message: "Found!",
  data: [
    {
      id: <id>,
      borrow_request_number: <string>,
      borrow_date: <date>,
      borror_return_date: <date>,
      borrow_reason: <string>,
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
      created_at: <timestamp>,
      updated_at: <timestamp>
    }
  ],
  pagination: {
    current_page: <int>,
    per_page: <int>,
    total_page: <int>,
    total_data: <int>,
  }
}
```
{% endtab %}
{% endtabs %}
