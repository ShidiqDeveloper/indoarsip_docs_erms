# Autentikasi

## Login

<mark style="color:green;">`POST`</mark> `/login`

Endpoint untuk melakukan login ke dashboard

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Body**

| Name         | Type   | Description |
| ------------ | ------ | ----------- |
| `email`      | string |             |
| `password`   | string |             |
| remember\_me | bool   |             |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Success",
  data: {
    token: <string>,
    expired_in: <int>
  }
}
```
{% endtab %}

{% tab title="401" %}
```json
{
  code: 401,
  status: false,
  message: "Email / Password yang anda masukan salah!",
  data: null
}
```
{% endtab %}
{% endtabs %}
