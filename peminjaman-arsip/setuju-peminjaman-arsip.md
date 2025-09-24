# Setuju Peminjaman Arsip

<mark style="color:green;">`PUT`</mark>`/borrow-requests/{id_borrow}/approve`

Endpoint untuk setujui peminjaman arsip. Set workflow\_status\_id menjadi 6

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
  message: "Berhasil menyetujui peminjaman arsip!",
  data: NULL
}
```
{% endtab %}
{% endtabs %}

