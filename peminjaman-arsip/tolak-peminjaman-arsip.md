# Tolak Peminjaman Arsip

<mark style="color:green;">`PUT`</mark>`/borrow-requests/{id_borrow}/reject`

Endpoint untuk setujui peminjaman arsip. Set workflow\_status\_id = 7

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

#### Body

| Name           | Type   | Description          |
| -------------- | ------ | -------------------- |
| reject\_reason | string | Keterangan penolakan |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  status: true,
  status_code: 200,
  message: "Berhasil menolak peminjaman arsip!",
  data: NULL
}
```
{% endtab %}
{% endtabs %}
