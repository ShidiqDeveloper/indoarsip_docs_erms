---
description: Endpoint untuk mengedit data arsip
---

# Edit Arsip Aktif

<mark style="color:green;">`POST`</mark> `/arhives-active`

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

```
{
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
  storage_location_id: <int>
}
```

| Name                      | Type   | Description                             | Validation                                                                  |
| ------------------------- | ------ | --------------------------------------- | --------------------------------------------------------------------------- |
| archive\_number           | string | Nomor arsip                             | required\|string\|max:255                                                   |
| indeks\_archive           | number | Indeks Arsip                            | required\|string\|max:255                                                   |
| clasification\_code\_id   | number | Ambil dari data master kode klasifikasi | required\|number\|exists:classification\_codes,id                           |
| archive\_name             | string | Nama Arsip                              | required\|string\|max:255                                                   |
| description\_archive      | string | Keterangan Arsip                        | required\|string\|max:300                                                   |
| owner\_role\_created      | number | Role pencipta arsip                     | required\|number\|exists:roles,id                                           |
| owner\_unit\_pengolah\_id | number | Arsip milik unit pengolah mana          | required\|number\|exists:organization\_units,id                             |
| count\_archive            | number | Jumlah arsip                            | required\|number                                                            |
| development\_level        | string | Tingkat perkembangan arsip              | required\|string\|enum:"Asli", "Copy"                                       |
| physical\_character       | string | Karateristik Fisik                      | required\|string\|enum:"Kertas", "Film", "Foto", "CD/DVD", "USB", "Lainnya" |
| languange                 | string | Bahasa isi arsip                        | required\|string\|max:255                                                   |
| hash\_value               | string | Nilai hash arsip                        | required\|string                                                            |
| storage\_location\_id     | number | Lokasi fisik arsip                      | required\|number\|exists:archive\_storage\_locations,id                     |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Berhasil mengedit arsip!",
  data: Null
}
```
{% endtab %}
{% endtabs %}

