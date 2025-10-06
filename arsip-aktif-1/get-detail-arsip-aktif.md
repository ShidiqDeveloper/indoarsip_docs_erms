---
description: Endpoint untuk mendapatkan detail arsip aktif
---

# Get Detail Arsip Aktif

<mark style="color:green;">`POST`</mark> `/archives-active/{id}`

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
  message: "Found",
  data: {
    id: <int>,
    archive_name: <string>,
    archive_number: <string>,
    indeks_archive: <string>,
    start_date_active: <date>,
    end_date_active: <date>,
    description_archive: <string|null>,
    count_archive: <int>,
    development_level: <string>,
    physical_character: <string>,
    language: <string>,
    hash_value: <string>,
    clasification_code_id: {
      id: <int>,
      arsip_type: <string>,
      code: <string>,
    },
    unit_pengolah: {
      id: <int>,
      code: <string>,
      organization: <string>
    },
    status: {
      id: <int>,
      archive_status: <string>,
      color: <string>,
    },
    storage_location: {
      id: <int>,
      location_name: <string>,
    },
    role_created: {
      id: <int>,
      role_name: <string>
    },
    relations: [
      {
        id: <int>,
        archive: {
          archive_name: <string>,
          archive_number: <string>,
        },
        relation_type: {
          id: <int>,
          relation_type: <string>,
        },
        note: <string>
      }
    ],
    created_at: <timestamp>,
    updated_at: <timestamp>,
  },
}
```
{% endtab %}
{% endtabs %}
