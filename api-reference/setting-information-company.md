# Setting Information Company

## Get Information Company

<mark style="color:green;">`GET`</mark>`/settings/company`

This endpoint for get information company

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
    company_name: <string>,
    company_email: <string>,
    company_phone: <int>,
    company_address: <string>,
    company_logo: <string>
  },
}
```
{% endtab %}
{% endtabs %}

## Update Information Company

<mark style="color:green;">`PUT`</mark>`/settings/company`

This endpoint for update company information

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name             | Type   | Description        | validation                         |
| ---------------- | ------ | ------------------ | ---------------------------------- |
| `company_name`   | string | Name of company    | required\|string\|\|max:200        |
| company\_email   | string | Email of company   | required\|string\|\|max:200\|email |
| company\_phone   | number | Phone of company   | required\|number\|max:20           |
| company\_logo    | file   | Logo of company    | required\|file\|image\|max:5048    |
| company\_address | string | Address of company | required\|string\|max:300          |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Sukses mengupdate informasi perusahaan!",
  data: {
    company_name: <string>,
    company_email: <string>,
    company_phone: <int>,
    company_address: <string>,
    company_logo: <string>
  },
}
```
{% endtab %}
{% endtabs %}

