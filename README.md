# checkup
CLI to run simple health checks against endpoints 

---
## Example Usage :


``` bash
checkup listen -e https://google.com # default code is 200
checkup listen -c 200 -e https://google.com
checkup listen --code 302 --endpoint https://potatoe.com/farm
checkup exam -f list.json
checkup exam --file list.yml
checkup listen -e https://google.com -u noodle -p soup
```

## Exam File Example :

### Yaml
``` yaml
name: Test Name
endpoint: https://duckduckgo.com
tests:
  - code: 200
    paths:
      - /farm
      - /something
      - /else
  - code: 404
    paths:
      - /this
      - /not
      - /found
```

``` json
{
  "name": "Exam Name",
  "endpoint": "https://google.com",
  "tests": [
    {
      "code": 200,
      "paths": [
          "/farm",
          "/something",
          "/else"
      ]
    },
    {
      "code": 404,
        "paths": [
          "/this",
          "/not",
          "/found"
      ]
    }
  ]
}
```