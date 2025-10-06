# Perubahan Status Workflow

<mark style="color:green;">`PUT`</mark> `/borrow-requests/{id_borrow}/workflow-status/{id_workflow}`&#x20;

Endpoint untuk mengubah status workflow dari permintaan peminjaman arsip

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

#### Body

```
{
    reject_reason: <string> // Opsional jika status yang di set adalah reject
}
```

| Name           | Type   | Description    | Validation                                     |
| -------------- | ------ | -------------- | ---------------------------------------------- |
| reject\_reason | string | Alasan ditolak | required jika status yang dituju adalah reject |

**Response**

{% tabs %}
{% tab title="200" %}
<pre class="language-json"><code class="lang-json">{
  code: 200,
  status: true,
  message: "Berhasil mengubah status!",
  data: {
<strong>    id: &#x3C;id>,
</strong>    borrow_request_number: &#x3C;string>,
    borrow_date: &#x3C;date>,
    borror_return_date: &#x3C;date>,
    borrow_reason: &#x3C;string>,
    file_attachment: &#x3C;string|null>,
    workflow_reject_reason: &#x3C;string|null>,
    user_borrow: {
      id: &#x3C;int>,
      name: &#x3C;string>,
    },
    workflow_status: {
      id: &#x3C;int>,
      status_name: &#x3C;string>,
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
        borrow_status: {
          id: &#x3C;int>,
          status: &#x3C;string>
        },
        storage_location: {
          id: &#x3C;int>,
          location_name: &#x3C;string>,
        },
      }
    ]
    created_at: &#x3C;timestamp>,
    updated_at: &#x3C;timestamp>
  }
}
</code></pre>
{% endtab %}
{% endtabs %}
