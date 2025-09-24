# Edit permintaan peminjaman arsip

## Create a new user

<mark style="color:green;">`PUT`</mark>`/borrow-requests/{id_borrow}`

Endpoint untuk edit permintaan peminjaman arsip

**Headers**

| Name          | Value                 |
| ------------- | --------------------- |
| Content-Type  | `multipart/form-data` |
| Authorization | `Bearer <token>`      |

**Body**

```
{
    user_id: <int>,
    borrow_date: <string>,
    borrow_return_date: <string>,
    archive_id: [1,2,...],
}
```

| Name                  | Type   | Description          | Validasi                                                       |
| --------------------- | ------ | -------------------- | -------------------------------------------------------------- |
| user\_id              | number | Nama peminjam        | required\|number\|exists:users,id                              |
| borrow\_date          | string | Tanggal Peminjaman   | required\|date\_format:Y-m-d                                   |
| borrowr\_return\_date | string | Tanggal Pengembalian | required\|date\_format:Y-m-d                                   |
| archive\_id           | array  | Arsip yang dipinjam  | required\|array\|exists:archives,id                            |
| file\_attachment      | file   | Lampiran File        | nullabel\|file\|mimes:docx,pdf,xls,xlsx,png,jpeg,jpg\|max:50MB |

**Response**

{% tabs %}
{% tab title="201" %}
```json
{
  status: true,
  status_code: 201,
  message: "Berhasil mengedit permintaan peminjaman arsip!",
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
