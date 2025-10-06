---
description: Endpoint untuk menambah data arsip aktif
---

# Penambahan Arsip Aktif

<mark style="color:green;">`POST`</mark> `/arhives-active`

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

```
{
  in_id: <string>, // Wajib ada setelah menambahkan arsip lebih dari 1x
  only_first: <bool>,
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
  languange: <string>,
  hash_value: <string>,
  storage_location_id: <int>,
  relations: [
    {
      archive_relation_id: <int>,
      relation_type_id: <int>,
      note_relation: <string>,
    }
  ]
}
```

| Name                            | Type   | Description                                                                                          | Validation                                                                  |
| ------------------------------- | ------ | ---------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| in\_id                          | number | Group ID saat penambahan arsip                                                                       | opsional\|number                                                            |
| only\_first                     | bool   | Indikasi apakah penambahan arsip lebih dari 1 atau tidak. Jika sudah ada in\_id maka ini tidak perlu | opsional\|bool                                                              |
| archive\_number                 | string | Nomor arsip                                                                                          | required\|string\|max:255                                                   |
| indeks\_archive                 | number | Indeks Arsip                                                                                         | required\|string\|max:255                                                   |
| clasification\_code\_id         | number | Ambil dari data master kode klasifikasi                                                              | required\|number\|exists:classification\_codes,id                           |
| archive\_name                   | string | Nama Arsip                                                                                           | required\|string\|max:255                                                   |
| description\_archive            | string | Keterangan Arsip                                                                                     | required\|string\|max:300                                                   |
| owner\_role\_created            | number | Role pencipta arsip                                                                                  | required\|number\|exists:roles,id                                           |
| owner\_unit\_pengolah\_id       | number | Arsip milik unit pengolah mana                                                                       | required\|number\|exists:organization\_units,id                             |
| count\_archive                  | number | Jumlah arsip                                                                                         | required\|number                                                            |
| development\_level              | string | Tingkat perkembangan arsip                                                                           | required\|string\|enum:"Asli", "Copy"                                       |
| physical\_character             | string | Karateristik Fisik                                                                                   | required\|string\|enum:"Kertas", "Film", "Foto", "CD/DVD", "USB", "Lainnya" |
| languange                       | string | Bahasa isi arsip                                                                                     | required\|string\|max:255                                                   |
| hash\_value                     | string | Nilai hash arsip                                                                                     | required\|string                                                            |
| storage\_location\_id           | number | Lokasi fisik arsip                                                                                   | required\|number\|exists:archive\_storage\_locations,id                     |
| relations                       | array  | Indikasi apakah ada tunjuk silang arsip                                                              | required\|array                                                             |
| relations.archive\_relation\_id | number | Arsip yang berelasi                                                                                  | number\|exists:archives,id                                                  |
| relations.relation\_type\_id    | number | Relasi arsip tunjuk silang                                                                           | number\|exists:relation\_archive\_types,id                                  |
| relations.note\_relation        | string | Catatan dari relasi arsip                                                                            | string\|max:255                                                             |

**Response**

{% tabs %}
{% tab title="200" %}
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
{% endtabs %}

