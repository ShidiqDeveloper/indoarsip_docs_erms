# Get Sifat Kerahasiaan Arsip

<mark style="color:green;">`GET`</mark> `/archive-`confidentialities

Endpoint untuk mendapatkan sifat kerahasiaan arsip

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
  message: "Found!",
  data: [
    {
      id: <int>,
      name: <string>,
      created_at: <datetime>,
      updated_at: <datetime>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}
