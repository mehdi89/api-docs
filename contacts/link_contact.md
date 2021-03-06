# Link user with contact

This endpoint will link a contact with given user and will sync that to tieit.


## Resource

```
GET /contacts/connect/{email}
```

## Parameters


URI Parameter | Type   | Required | Description
:------------ | :----- | :------- | :-----------------------------------------------------------------------------------
email         | string | yes      | the contact you want to link with
token         | string | yes      | Use the JWT token returned after successfully successfully logging into the account.

## Example

### Request

--------------------------------------------------------------------------------

```
curl ""
```

### Response

--------------------------------------------------------------------------------

**Status-Code:** `200 OK`

```json
{
  "message": "Linked with contact successfully",
  "status_code": 200,
  "data": {
    "user_id": 8,
    "contact_email": "hasanmehdi89+5@gmail.com",
    "id": 15
  }
}
```

```json
{
  "message": "Contact linked successfully, but unable to sync with tieit",
  "status_code": 200,
}
```

```json
{
  "message": "Contact linked successfully, already have contact with this email in tieit",
  "status_code": 200,
}
```

```json
{
  "message": "The contact is already linked with the user",
  "status_code": 200,
}
```

### Error Responses

--------------------------------------------------------------------------------

**Status-Code:** `401 Could not decode token`

```json
{
  "message": "Could not decode token: The token \"eyJ0eXAiOiJKV1iLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOjE3MiwiaXNzIjoiaHR0cDpcL1wvY29uZi1zdGcucHJvaHViLmlvXC9hcGlcL2F1dGhcL2xvZ2luIiwiaWF0IjoxNDg4NjU5MjQ4LCJleHAiOjE0ODkwOTEyNDgsIm5iZiI6MTQ4ODY1OTI0OCwianRpIjoiMzk3NTFjNGQ0NWJmYWUwMTY5MjBjMGNkYTU0ZTI2MWUifQ.hQrXeXEnEhgflmRbfM0klQfLKS_q6Z-q4QfM-VajYhc\" is an invalid JWS",
  "status_code": 401,
}
```
