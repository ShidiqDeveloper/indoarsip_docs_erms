# Penambahan Arsip Vital

<mark style="color:green;">`POST`</mark> `/arhives-vitals`&#x20;

Endpoint untuk menambah permintaan arsip vital. Default status workflow adalah draft.&#x20;

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

```
{
  id_request: <string>, // Wajib ada setelah menambahkan arsip lebih dari 1x
  finish_input: <bool>, // Parameter input arsip selesai / masih ada input arsip lain
  archive_number: <string>,
  indeks_archive: <int>,
  clasification_code_id: <int>,
  archive_name: <string>,
  description_archive: <string>,
  owner_role_created: <int>,
  owner_unit_pengolah_id: <int>,
  count_archive: <int>,
  development_level: <string>,
  physical_character: <string>,
  confidentiality: <string>,
  protect_method_archive: [<string>, ...],
  languange: <string>,
  hash_value: <string>,
  storage_location_id: <int>
}
```

| Name                      | Type   | Description                                                                                                           | Validation                                                                  |
| ------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| id\_request               | number | Group ID saat penambahan arsip                                                                                        | opsional\|number                                                            |
| finish\_input             | bool   | Indikasi apakah penambahan arsip lebih dari 1 atau tidak. Jika penambahan arsip hanya 1x, maka awal input adalah true | opsional\|bool                                                              |
| archive\_number           | string | Nomor arsip                                                                                                           | required\|string\|max:255                                                   |
| indeks\_archive           | number | Indeks Arsip                                                                                                          | required\|string\|max:255                                                   |
| clasification\_code\_id   | number | Ambil dari data master kode klasifikasi                                                                               | required\|number\|exists:classification\_codes,id                           |
| archive\_name             | string | Nama Arsip                                                                                                            | required\|string\|max:255                                                   |
| description\_archive      | string | Keterangan Arsip                                                                                                      | required\|string\|max:300                                                   |
| owner\_role\_created      | number | Role pencipta arsip                                                                                                   | required\|number\|exists:roles,id                                           |
| owner\_unit\_pengolah\_id | number | Arsip milik unit pengolah mana                                                                                        | required\|number\|exists:organization\_units,id                             |
| count\_archive            | number | Jumlah arsip                                                                                                          | required\|number                                                            |
| development\_level        | string | Tingkat perkembangan arsip                                                                                            | required\|string\|enum:"Asli", "Copy"                                       |
| physical\_character       | string | Karateristik Fisik                                                                                                    | required\|string\|enum:"Kertas", "Film", "Foto", "CD/DVD", "USB", "Lainnya" |
| languange                 | string | Bahasa isi arsip                                                                                                      | required\|string\|max:255                                                   |
| hash\_value               | string | Nilai hash arsip                                                                                                      | required\|string                                                            |
| storage\_location\_id     | number | Lokasi fisik arsip                                                                                                    | required\|number\|exists:archive\_storage\_locations,id                     |
| confidentiality           | string | Tingkat kerahasiaan arsip                                                                                             | required\|string                                                            |
| protect\_method\_archive  | array  | Metode perlindungan arsip                                                                                             | required\|array                                                             |

**Response**

{% tabs %}
{% tab title="201 (finish = false)" %}
```json
{
  code: 201,
  status: true,
  message: "Berhasil menambahkan arsip!",
  data: {
    id: <int>
  }
}
```
{% endtab %}

{% tab title="201 (finish = true)" %}
```
{
  code: 201,
  status: true,
  message: "Sukses menambahkan arsip vital!",
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

