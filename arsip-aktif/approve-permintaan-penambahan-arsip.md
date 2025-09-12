# Approve Permintaan Penambahan Arsip

<mark style="color:green;">`PUT`</mark> `/archives-active/ins/{id_in}/approve`

Endpoint ini khusus corsec/unit kearsipan me-approve arsip yang masuk jika sudah sesuai semua

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
  message: "Berhasil menyetujui arsip!",
  data: NULL
}
```
{% endtab %}
{% endtabs %}
