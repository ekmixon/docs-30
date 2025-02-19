# List Observables

List observables of an *Alerts*.

## Query

```plain
POST /api/v0/query?name
```

##  Request Body Example

!!! Example "" 
    
    List last 15 added observables:

    ```json
    {
      "query": [
        {
          "_name": "getAlert",
          "idOrName": "{id}"
        },
        {
          "_name": "observables"
        },
        {
          "_name": "sort",
          "_fields": [
            {
              "startDate": "desc"
            }
          ]
        },
        {
          "_name": "page",
          "from": 0,
          "to": 15,
          "extraData": [
            "seen"
          ]
        }
      ]
    }
    ```

    With:

    - `id`: id of the *Alert*

## Response

### Status codes

- `200`: if query is run successfully
- `401`: Authentication error

### ResponseBody Example

!!! Example ""

    ```json
    [
      ...
      {
        "_id": "~11111462234",
        "id": "~11111462234",
        "_type": "Observable",
        "_createdBy": "system@thehive.local",
        "_createdAt": 1629309258431,
        "dataType": "other",
        "data": "1.2.3.4",
        "startDate": 1629309258431,
        "tlp": 0,
        "ioc": false,
        "sighted": false,
        "reports": {},
        "stats": {}
      }
      ...
    ]
    ```