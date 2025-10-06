# Perubahan Status Workflow

<mark style="color:green;">`PUT`</mark> `/archives-active/ins/{id_in}/workflow-status/{id_workflow}`&#x20;

Endpoint untuk mengubah status workflow dari permintaan penambahan arsip aktif

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

#### Body

```
{
    reject_reason: <string> // Opsional jika status yang di set adalah reject
}
```

| Name           | Type   | Description    | Validation                                     |
| -------------- | ------ | -------------- | ---------------------------------------------- |
| reject\_reason | string | Alasan ditolak | required jika status yang dituju adalah reject |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Berhasil mengubah status!",
  data: {
    id: <int>,
    approved_date: <date|null>,
    count_archive: <int>,
    count_revision: <int>,
    reason_reject: <string|null>,
    link_letter_list_archives: <string|null>,
    link_letter_minutes: <string|null>,
    link_letter_relationship: <string|null>,
    user_create: {
      id: <int>,
      name: <string>,
    },
    workflow_status: {
      id: <int>,
      status_name: <string>,
    },
    owner_role: {
      id: <int>,
      role_name: <string>
    },
    unit_pengolah: {
      id: <int>,
      code: <string>,
      organization: <string>
    },
    archives: [
      {
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
        status: {
          id: <int>,
          archive_status: <string>,
          color: <string>,
        },
        storage_location: {
          id: <int>,
          location_name: <string>,
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
      }
    ]
  }
}
```
{% endtab %}
{% endtabs %}
