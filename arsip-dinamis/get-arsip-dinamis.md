---
description: Endpoint ini untuk menambah arsip aktif
---

# Get Arsip Dinamis

<mark style="color:green;">`GET`</mark>`/arhives-dynamics`

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name                    | Type   | Description                                            |
| ----------------------- | ------ | ------------------------------------------------------ |
| keyword                 | string | Filter untuk nama arsip/nomor dokumen/keterangan arsip |
| archive\_type\_id       | number | Filter berdasarkan jenis arsip                         |
| archive\_status\_id     | number | Filter berdasarkan status arsip                        |
| unit\_pengolah\_id      | number | Filter bedasarkan unit pengolah                        |
| clasification\_code\_id | number | Filter berdasarkan kode klasifikasi arsip              |
| page                    | number | Filter halaman ke-n                                    |

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
