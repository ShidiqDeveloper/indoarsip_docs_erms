---
description: Endpoint ini untuk mendapatkan list arsip vital
---

# Get Arsip Vital

<mark style="color:green;">`GET`</mark>`/arhives-vitals`

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name    | Type   | Description                                            |
| ------- | ------ | ------------------------------------------------------ |
| keyword | string | Filter untuk nama arsip/nomor dokumen/keterangan arsip |
| page    | number | Filter halaman ke-n                                    |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Found",
  data: {
    data: [
      {
        id: <int>,
        archive_name: <string>,
        archive_number: <string>,
        start_date_active: <date>,
        end_date_active: <date>,
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
        protect_method_archive: <string>,
        storage_location: {
          id: <int>,
          location_name: <string>,
        },
        created_at: <timestamp>,
        updated_at: <timestamp>,
      }
    ],
    pagination: {
      current_page: <int>,
      per_page: <int>,
      total_page: <int>,
      total_data: <int>
    }
  },
}
```
{% endtab %}
{% endtabs %}
