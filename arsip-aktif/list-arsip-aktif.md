---
description: Endpoint ini untuk menambah arsip aktif
---

# List Arsip Aktif

<mark style="color:green;">`GET`</mark>`/arhives-active`

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name                | Type   | Description                                            |
| ------------------- | ------ | ------------------------------------------------------ |
| unit\_pengolah\_id  | number | Filter bedasarkan unit pengolah                        |
| `archive_status_id` | number | Filter berdasarkan status arsip aktif                  |
| keyword             | string | Filter untuk nama arsip/nomor dokumen/keterangan arsip |

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
        status: {
          id: <int>,
          archive_status: <string>,
          color: <string>,
        },
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
