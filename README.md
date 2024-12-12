# API Endpoint
``` 
GET /time/add
``` 
  *This endpoint adds time units to a provided timestamp.*

## Request Parameters
*timestamp*  (required): The base date for which time units will be added.

##### Example: 2016-10-10
***years*** (optional): Number of years to add.

***months*** (optional): Number of months to add.

***days***(optional): Number of days to add.

***hours*** (optional): Number of hours to add.

***minutes*** (optional): Number of minutes to add.

***seconds*** (optional): Number of seconds to add.

***milliseconds*** (optional): Number of milliseconds to add.

***locale*** (optional): The locale used for formatting and parsing the timestamp.

***format*** (optional): Defines the format of the response (e.g., ISO, RFC).

***trict*** (optional): If set to true, the API will strictly validate inputs (defaults to false).

# Sample Request

```
GET https://postman-echo.com/time/add?timestamp=2016-10-10&years=100&months=5&days=10
```
This request adds 100 years, 5 months, and 10 days to the timestamp 2016-10-10.

# Response
Successful Response (HTTP Status 200)
```
{
  "sum": "2116-10-10T00:00:00.000Z"
}
```
This response indicates an error with the request, such as an invalid date format or unsupported time units.

Erroneous request (code 400):
```
{
"level": "error",
...
}
```

## Notes
It is recommended to add tests to Postman for verification:
* Response status ( ```pm.response.to.have.status(200)``` ).
* The ```sum``` or level fields in the response body (``` pm.expect(...)```).
