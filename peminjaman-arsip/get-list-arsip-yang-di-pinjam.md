# Get List Arsip Yang Di pinjam

<mark style="color:green;">`POST`</mark> `/users`

Endpoint untuk mendapatkan list arsip yang sedang dipinjam

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name               | Type   | Description                                                   |
| ------------------ | ------ | ------------------------------------------------------------- |
| `keyword`          | string | Filter berdasarkan nama dokumen, nomor dokumen, nama peminjam |
| `borrow_status_id` | number | Filter berdasarkan status peminjaman                          |
| page               | number | Filter halaman ke-n                                           |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  status: true,
  status_code: 200,
  message: "Ditemukan!",
  data: [
    {
      id: <id>,
      borrow_date: <date>,
      borror_return_date: <date>,
      borrow_status: {
        id: <int>,
        status: <int>,
      },
      archive: {
        id: <id>,
        archive_name: <string>,
        archive_number: <string>,
      },
      borrow_requests: {
        user_borrow: {
          id: <int>,
          name: <string>,
        },
        organization: {
          id: <int>,
          code: <int>,
          name: <string>,
        },
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
