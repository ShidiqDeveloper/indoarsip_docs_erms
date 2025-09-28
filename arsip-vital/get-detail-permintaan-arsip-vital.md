---
description: Endpoint untuk mendapatkan data detail dari arsip masuk / batch
---

# Get Detail Permintaan Arsip Vital

## Create a new user

<mark style="color:green;">`GET`</mark> `/arhives-vitals/requests/{id_request}`

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
  data: {
    id: <int>,
    approved_date: <date|null>,
    count_archive: <int>,
    count_revision: <int>,
    reason_reject: <string|null>,
    user_create: {
      id: <int>,
      name: <string>,
    },
    workflow_status: {
      id: <int>,
      status_name: <string>,
    },
    archives: [
      {
        id: <int>,
        archive_name: <string>,
        archive_number: <string>,
        indeks_archive: <string>,
        description_archive: <string|null>,
        count_archive: <int>,
        development_level: <string>,
        physical_character: <string>,
        confidentiality: <string>,
        protect_method_archive: [
          <string>,
          <string>,
          ...
        ],
        language: <string>,
        hash_value: <string>,
        clasification_code_id: {
          id: <int>,
          arsip_type: <string>,
          code: <string>,
        }
      }
    ]
  }
}
```
{% endtab %}
{% endtabs %}
