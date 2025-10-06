---
description: Endpoint untuk mencari arsip
---

# Search Archive

<mark style="color:green;">`GET`</mark>`/search-archives`

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name              | Type   | Description                                                |
| ----------------- | ------ | ---------------------------------------------------------- |
| `keyword`         | string | Cari berdasarkan nama arsip, nomor arsip, kode klasifikasi |
| archive\_type\_id | number | Filter berdasarkan tipe arsip                              |

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
      archive_name: <string>,
      archive_number: <string>,
      clasification_code_id: {
        id: <int>,
        arsip_type: <string>,
        code: <string>,
      },
    }
  ]
}
```
{% endtab %}
{% endtabs %}
