# Menambah Data Pengembalian Barang

<mark style="color:green;">`POST`</mark> `/return-borrows`

Endpoint untuk menambahkan pengembalian barang

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

```
{
  borrow_request_id: <int>,
  return_note: <string>,
  archive_ids: [<int>, <int>, ...]
}
```

| Name                | Type   | Description                   |
| ------------------- | ------ | ----------------------------- |
| `borrow_request_id` | number | ID Dari permintaan peminjaman |
| `return_note`       | string | Catatan jika ada              |
| archive\_ids        | array  | Arsip yang dikembalikan       |

**Response**

{% tabs %}
{% tab title="201" %}
<pre class="language-json"><code class="lang-json"><strong>{
</strong>  code: 201,
  status: true,
  message: "Berhasil membuat pengembalian arsip!",
  data: {
    id: &#x3C;int>,
    return_number: &#x3C;string>,
    return_date: &#x3C;date>,
    return_note: &#x3C;string|null>,
    reject_reason: &#x3C;string|null>,
    workflow_status: {
      id: &#x3C;int>,
      status_name: &#x3C;string>,
    },
    borrow_request: {
      borrow_request_number: &#x3C;string>,
      borrow_date: &#x3C;date>,
      borror_return_date: &#x3C;date>,
      borrow_reason: &#x3C;string>,
    },
    user_borrow: {
      id: &#x3C;int>,
      name: &#x3C;string>,
    },
    organization: {
      id: &#x3C;int>,
      code: &#x3C;int>,
      name: &#x3C;string>,
    },
    archives: [
      {
        id: &#x3C;int>,
        archive_name: &#x3C;string>,
        archive_code: &#x3C;string>,
        clasification_code_id: {
          id: &#x3C;int>,
          arsip_type: &#x3C;string>,
          code: &#x3C;string>,
        },
        unit_pengolah: {
          id: &#x3C;int>,
          code: &#x3C;string>,
          organization: &#x3C;string>
        },
      }
    ]
  }
}
</code></pre>
{% endtab %}
{% endtabs %}
