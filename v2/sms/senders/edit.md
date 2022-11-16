## Edit Sender-ids

Edit sender-ids using post method under your account

#### API Endpoint

```
{domain}/api/{version}/
```

#### PUT

```
{endpoint}sms/senders/{id}
```

#### PARAMETERS

| Name         | optional | Descriptions                                                                                 |
| ------------ | -------- | -------------------------------------------------------------------------------------------- |
| country_code | No       | For which country this sender belongs to. 2 letters                                          |
| entity_id    | No       | Input the entity id (required for india)                                                     |
| entity_name  | No       | Company name whom this sender belongs to (required for india)                                |
| service      | No       | The short code of the service name. ex: (MKT) [full list](/docs/{version}/#content-products) |

#### Example Request

```
curl -X PUT \
  {endpoint}sms/senders/ff467e28-7170-4a72-952e-c999cxxxxxx \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer 5b02112fb7xxxxxxxxx' \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  -d entity_name=xxxxx \
  -d entity_id=xxxxx \
  -d service=MKT \
  -d country_code=IN
```

#### Example Response

```json
{
    "status": "OK",
    "code": 200,
    "message": "Sender Updated Successfully",
    "data": {
        "id": "ff467e28-7170-4a72-952e-c999cxxxxxx",
        "name": "SENDER",
        "service": {
            "id": 55,
            "display_name": "Global SMS",
            "name": "G"
        },
        "entity_name": "SAMPLE COMPANY",
        "entity_id": "123233434355345555",
        "header_id": null,
        "iso": "IN",
        "message": null,
        "document": null,
        "is_open": 0,
        "purpose": 1,
        "status": 1,
        "created_at": "2022-11-16T06:53:26.000000Z",
        "updated_at": "2022-11-16T06:55:55.000000Z"
    }
}
```
