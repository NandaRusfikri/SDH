# API Spec SDH V2

## Get List Unit

Request :

- Method : GET
- Endpoint : `localhost:6969/unit/list`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- form-body JSON :

```json
{
  "search": "search code",
  "limit": 15,
  "offset": 3,
  "order_field": "id|asc",
  "id_user": 7
}
```

Response :

```json
{
  "message": "get list unit successfully",
  "count": 10,
  "items": [
    {
      "id": 9,
      "unit_name": "U.FH.AD.SS.F11A",
      "id_status": 1,
      "status": "Available",
      "created_at": "2021-07-17 20:52:28.205326"
    },
    {
      "id": 10,
      "unit_name": "U.FH.AD.SS.F12B",
      "id_status": 2,
      "status": "Used",
      "created_at": "2021-07-17 20:52:28.205326"
    }
  ]
}
```

## Get Detail Unit

Request :

- Method : POST
- Endpoint : `localhost:6969/unit?id=9`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- form-body JSON :

```json
{
  "id_unit": 9 // id_unit
}
```

Response :

```json
{
  "message": "get detail unit successfully",
  "item": {
    "id": 9,
    "id_status": 1,
    "status": "Available",
    "garden": "creation",
    "mansion": "peacefulness",
    "space_no": 7,
    "unit_purchase_date": "2021-08-12 10:52:11",
    "unit_purchase_value": "Rp. 80.000.000",
    "id_status_unit": 2,
    "status_unit": "Belum Lunas",
    "slot": [
      {
        "id": 1,
        "name": "Jhon",
        "date_of_death": "2021-08-12 10:52:11",
        "id_status": 1,
        "status": "Available"
      },
      {
        "id": 2,
        "name": "Deni",
        "date_of_death": "2021-08-12T10:52:11.062483+07:00",
        "id_status": 2,
        "status": "Not Available"
      }
    ]
  },
  "additional_data": {
    "sertifikat_unit": "url/file",
    "siteplan": "url/img"
  },
  "future_care": [
    {
      "id": 11,
      "name": "Alexandria Miller",
      "date_of_birth": "30/06/1990",
      "sum_insured": "Rp 80.000.000"
    },
    {
      "id": 12,
      "name": "Joe Miller",
      "date_of_birth": "30/06/1990",
      "sum_insured": "Rp 60.000.000"
    }
  ]
}
```

## Get List Slot Unit

Request :

- Method : POST
- Endpoint : `localhost:6969/unit/slot/list`
- Header :

  - Content-Type: application/json
  - Accept: application/json

- form-body JSON :

```json
{
  "id_unit": 1, // id_unit,
  "search": "search name",
  "limit": 15,
  "offset": 3,
  "order_field": "id|asc",

```

Response :

```json
{
  "count": 5,
  "items": [
    {
      "id": 1,
      "name": "Jhon",
      "date_of_death": "2021-08-12 10:52:11",
      "id_status": 1,
      "status": "Available"
    },
    {
      "id": 2,
      "name": "Deni",
      "date_of_death": "2021-08-12 10:52:11",
      "id_status": 2,
      "status": "Not Available"
    }
  ]
}
```



## Get List Future Care

Request :

- Method : POST
- Endpoint : `localhost:6969/unit/future_care/list`
- Header :

  - Content-Type: application/json
  - Accept: application/json

- form-body JSON :

```json
{
  "id_unit": 1, // id_unit,
  "search": "search name",
  "limit": 15,
  "offset": 3,
  "order_field": "id|asc",
}
```

Response :

```json
{
  "count": 5,
  "future_care": [
    {
      "id": 11,
      "name": "Alexandria Miller",
      "date_of_birth": "30-06-1990",
      "sum_insured": "Rp 80.000.000"
    },
    {
      "id": 12,
      "name": "Joe Miller",
      "date_of_birth": "30-06-1990",
      "sum_insured": "Rp 60.000.000"
    }
  ]
}
```

## Get List Family Tree

Request :

- Method : POST
- Endpoint : `localhost:6969/family_tree/list`
- Header :

  - Content-Type: application/json
  - Accept: application/json

- form-body JSON :

```json
{
  "search": "search by name, email, phone",
  "limit": 15,
  "offset": 3,
  "order_field": "id|asc"
}
```

Response :

```json
{
  "count": 5,
  "items": [
    {
      "id": 11,
      "name": "Dimas Nayoan",
      "email": "dimas@gmail.com",
      "phone": "0812345678",
      "id_relation": 2,
      "relation": "Ibu",
      "photo": "path url photo",
      "created_at": "30-03-2021 10:10:10"
    },
    {
      "id": 11,
      "name": "Jihan Nayoan",
      "email": "jihan@gmail.com",
      "phone": "0812345678",
      "id_relation": 2,
      "relation": "kakak",
      "photo": "path url photo",
      "created_at": "30-03-2021 10:10:10"
    }
  ]
}
```


## Create Family Tree

Request :

- Method : POST
- Endpoint : `localhost:6969/family_tree/create`
- Header :

  - Content-Type: application/json
  - Accept: application/json

- form-body JSON :

```json
{
  "id_user": 1, //
  "name": "Leonel Dimas",
  "email": "dimas@gmail.com",
  "phone": "0812345678",
  "id_relation": 1,
  "photo": "path photo"
}
```

Response :

```json
{
  "message": "success create family tree"
}
```


## Update Family Tree

Request :

- Method : PUT
- Endpoint : `localhost:6969/family_tree/update`
- Header :

  - Content-Type: application/json
  - Accept: application/json

- form-body JSON :

```json
{
  "id": 6, // id family tree
  "name": "Leonel Dimas",
  "email": "dimas@gmail.com",
  "phone": "0812345678",
  "id_relation": 1, // id relation ex ayah|ibu|nenek
  "photo": "path photo"
}
```

Response :

```json
{
  "message": "success update family tree"
}
```



## Delete Family Tree

Request :

- Method : DELETE
- Endpoint : `localhost:6969/family_tree/delete?id=7`
- Header :

  - Content-Type: application/json
  - Accept: application/json

- Query Params :

```yaml
id: 7 # id family tree
```

Response :

```json
{
  "message": "success delete family tree"
}
```
