---
description: >-
  Endpoint ini untuk mengecek apakah suatu module / aksi dapat diakses oleh user
  yang sedang login
---

# Check hak akses suatu module / aksi

<mark style="color:green;">`GET`</mark>`/rbac/modules/{id_module}/check`&#x20;

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Response**

{% tabs %}
{% tab title="200 (Dapat Diakses)" %}
```json
{
  code: 200,
  status: true,
  message: "Dapat diakses!",
  data: NULL,
}
```
{% endtab %}

{% tab title="403 (Tidak Dapat Diakses)" %}
```
{
  code: 403,
  status: false,
  message: "Forbidden!",
  data: NULL,
}
```
{% endtab %}
{% endtabs %}

