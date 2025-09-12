# Module Struktur Organisasi

## Get List Organization Tree View

<mark style="color:green;">`GET`</mark> `/organizations-tree`

Endpoint for get all organization for UI tree view

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
  data: [
    {
      id: <int>,
      code: <string>,
      level: <int>,
      organization: <string>,
      is_unit_kearsipan: <int>,
      is_unit_kerja: <int>,
      is_unit_pengolah: <int>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
      childs: [
        {
            id: <int>,
            code: <string>,
            level: <int>,
            organization: <string>,
            is_unit_kearsipan: <int>,
            is_unit_kerja: <int>,
            is_unit_pengolah: <int>,
            created_at: <timestamp>,
            updated_at: <timestamp>,
            childs: [
                {
                    id: <int>,
                    code: <string>,
                    level: <int>,
                    organization: <string>,
                    is_unit_kearsipan: <int>,
                    is_unit_kerja: <int>,
                    is_unit_pengolah: <int>,
                    created_at: <timestamp>,
                    updated_at: <timestamp>,
                }
            ]
        }
      ]
    }
  ]
}
```
{% endtab %}
{% endtabs %}

## Get List Organization

<mark style="color:green;">`POST`</mark> `/organizations`

Get all organization

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name                | Type | Description                                    |
| ------------------- | ---- | ---------------------------------------------- |
| `is_unit_kerja`     | int  | For filter organization in unit kerja only     |
| `is_unit_kearsipan` | int  | For filter organization in unit kearsipan only |
| is\_unit\_pengolah  | int  | For filter organization in unit pengolah only  |

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
      parent: <string>
      code: <string>,
      level: <int>
      organization: <string>,
      is_unit_kearsipan: <int>,
      is_unit_kerja: <int>,
      is_unit_pengolah: <int>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}

## Store New Organization

<mark style="color:green;">`POST`</mark> `/organizations`

Store new organization

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name                | Type   | Description                                 | Validation                                      |
| ------------------- | ------ | ------------------------------------------- | ----------------------------------------------- |
| `parent_id`         | int    | Parent of organization                      | required\|number\|exists:organization\_units,id |
| `code`              | string | Code for organization                       | required\|string\|unique\|max:200               |
| organization        | string | Name of organization                        | required\|string\|max:200                       |
| is\_unit\_pengolah  | int    | Indicator organization have unit pengolah   | sometimes\|number                               |
| is\_unit\_kearsipan | int    | Indication organization have unit kearsipan | sometimes\|number                               |
| is\_unit\_kerja     | int    | Indicator organization is unit kerja        | sometimes\|number                               |
| is\_active          | int    | Indicator for status active of organization | sometimes\|number                               |

**Response**

{% tabs %}
{% tab title="201" %}
```json
{
  code: 201,
  status: true,
  message: "Berhasil membuat struktur organisasi!",
  data: [
    {
      id: <int>,
      parent: <string>
      code: <string>,
      organization: <string>,
      is_unit_kearsipan: <int>,
      is_unit_kerja: <int>,
      is_unit_pengolah: <int>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}

## Get Record Centre List

<mark style="color:green;">`GET`</mark> `/record-centres`

Get all record centre

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name | Type   | Description           |
| ---- | ------ | --------------------- |
| name | string | Name of record centre |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Berhasil membuat struktur organisasi!",
  data: [
    {
      id: <int>,
      name: <string>,
      rc_level: <int>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ]
}
```
{% endtab %}
{% endtabs %}
