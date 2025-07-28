# Postman_collection


﻿

POST
Create auth for put, delete
{{base_url}}/auth
Generated from cURL: curl -X POST 
  https://restful-booker.herokuapp.com/auth 
  -H 'Content-Type: application/json' 
  -d '{
    "username" : "admin",
    "password" : "password123"
}'

﻿

Authorization
Basic Auth
Username
{{username}}
Password
{{password}}
Request Headers
Content-Type
application/json
token
Body
raw (json)
json
{
    "username" : "admin",
    "password" : "password123"
}
Example
Create auth for put, delete
Request
cURL
curl --location --globoff '{{base_url}}/auth' \
--header 'Content-Type: application/json' \
--data '{
    "username" : "admin",
    "password" : "password123"
}'
Response
Body
Headers (0)
Text
HTTP/1.1 200 OK

{
    "token": "abc123"
}
GET
GetbookingIDs
{{base_url}}/booking
Generated from cURL: curl -i https://restful-booker.herokuapp.com/booking﻿

﻿

Example
GetbookingIDs
Request
cURL
curl --location --globoff '{{base_url}}' \
--data ''
Response
Body
Headers (0)
View More
Text
HTTP/1.1 200 OK

[
  {
    "bookingid": 1
  },
  {
    "bookingid": 2
  },
  {
    "bookingid": 3
  },
  {
    "bookingid": 4
  }
]
GET
GetBookingID by name
{{base_url}}/auth/{{username}}/{{password}}
Generated from cURL: curl -i https://restful-booker.herokuapp.com/booking?firstname=sally&lastname=brown﻿

﻿

Authorization
Basic Auth
Username
{{username}}
Password
{{password}}
Query Params
test
{{username}}
GET
GetBookingID by ID
https://restful-booker.herokuapp.com/booking/194
Generated from cURL: curl -i https://restful-booker.herokuapp.com/booking/1﻿

﻿

GET
GetBookingID by ID
https://restful-booker.herokuapp.com/booking/3351
Generated from cURL: curl -i https://restful-booker.herokuapp.com/booking/1﻿

﻿

GET
GetBookingID by checkin and checkout
https://restful-booker.herokuapp.com/booking?checkin=2024-01-01&checkout=2024-01-02
Generated from cURL: curl -i https://restful-booker.herokuapp.com/booking?checkin=2014-03-13&checkout=2014-05-21﻿

﻿

Query Params
checkin
2024-01-01
checkout
2024-01-02
POST
Verify the response with valid username and password
{{base_url}}/booking
Generated from cURL: curl -X POST 
  https://restful-booker.herokuapp.com/booking 
  -H 'Content-Type: application/json' 
  -d '{
    "firstname" : "Jim",
    "lastname" : "Brown",
    "totalprice" : 111,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}'

﻿

Request Headers
Content-Type
application/json
Body
raw (json)
json
{
    "firstname" : "Jim",
    "lastname" : "Brown",
    "totalprice" : 111,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}
Example
Verify the response with valid username and password
Request
View More
cURL
curl --location --globoff '{{base_url}}/' \
--header 'Content-Type: application/json' \
--data '{
    "firstname" : "Jim",
    "lastname" : "Brown",
    "totalprice" : 111,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}'
Response
Body
Headers (0)
View More
Text
HTTP/1.1 200 OK

{
    "bookingid": 1,
    "booking": {
        "firstname": "Jim",
        "lastname": "Brown",
        "totalprice": 111,
        "depositpaid": true,
        "bookingdates": {
            "checkin": "2018-01-01",
            "checkout": "2019-01-01"
        },
        "additionalneeds": "Breakfast"
    }
}
PUT
Update the details
{{base_url}}/booking/2874
Generated from cURL: curl -X PUT 
  https://restful-booker.herokuapp.com/booking/1 
  -H 'Content-Type: application/json' 
  -H 'Accept: application/json' 
  -H 'Cookie: token=abc123' 
  -d '{
    "firstname" : "James",
    "lastname" : "Brown",
    "totalprice" : 111,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}'

﻿

Authorization
Basic Auth
Username
<username>
Password
{{vault:authorization-password}}
Request Headers
Content-Type
application/json
Accept
application/json
cookie
{{token}}
Body
raw (json)
json
{
    "firstname" : "hi",
    "lastname" : "ani",
    "totalprice" : 999,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-02",
        "checkout" : "2019-01-02"
    },
    "additionalneeds" : "Breakfast"
}
Example
Update the details
Request
View More
cURL
curl --location --request PUT 'https://restful-booker.herokuapp.com/booking/7486' \
--header 'Content-Type: application/json' \
--header 'Accept: application/json' \
--header 'Cookie: 879db3cd38ad211' \
--data '{
    "firstname" : "Mark",
    "lastname" : "tesla",
    "totalprice" : 999,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-02",
        "checkout" : "2019-01-02"
    },
    "additionalneeds" : "Breakfast"
}'
Response
Body
Headers (0)
Text
{
    "firstname": "Mark",
    "lastname": "tesla",
    "totalprice": 999,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2018-01-02",
        "checkout": "2019-01-02"
    },
    "additionalneeds": "Breakfast"
}
PATCH
Partial update
{{base_url}}/booking/{{bookingid}}
Generated from cURL: curl -X PATCH 
  https://restful-booker.herokuapp.com/booking/1 
  -H 'Content-Type: application/json' 
  -H 'Accept: application/json' 
  -H 'Cookie: token=abc123' 
  -d '{
    "firstname" : "James",
    "lastname" : "Brown"
}'

﻿

Authorization
Basic Auth
Username
{{username}}
Password
{{password}}
Request Headers
Content-Type
application/json
Accept
application/json
Body
raw (json)
json
{
    "firstname" : "eric",
    "lastname" : "martin1testing"
}
POST
Verify the response with firstname is missing
https://restful-booker.herokuapp.com/booking
Generated from cURL: curl -X POST 
  https://restful-booker.herokuapp.com/booking 
  -H 'Content-Type: application/json' 
  -d '{
    "firstname" : "Jim",
    "lastname" : "Brown",
    "totalprice" : 111,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}'

﻿

Request Headers
Content-Type
application/json
Body
raw (json)
json
{
    "firstname" : "",
    "lastname" : "Brown",
    "totalprice" : 111,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}
POST
verify the response with both name missing
https://restful-booker.herokuapp.com/booking
Generated from cURL: curl -X POST 
  https://restful-booker.herokuapp.com/booking 
  -H 'Content-Type: application/json' 
  -d '{
    "firstname" : "Jim",
    "lastname" : "Brown",
    "totalprice" : 111,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}'

﻿

Request Headers
Content-Type
application/json
Body
raw (json)
json
{
    "firstname" : "",
    "lastname" : "",
    "totalprice" : 111,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}
POST
Verify the response with totalprice missing
https://restful-booker.herokuapp.com/booking
Generated from cURL: curl -X POST 
  https://restful-booker.herokuapp.com/booking 
  -H 'Content-Type: application/json' 
  -d '{
    "firstname" : "Jim",
    "lastname" : "Brown",
    "totalprice" : 111,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}'

﻿

Request Headers
Content-Type
application/json
Body
raw (json)
json
{
    "firstname" : "Jim",
    "lastname" : "Brown",
    "totalprice" : ,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}
POST
Verify the response with depositpaid missing
https://restful-booker.herokuapp.com/booking
Generated from cURL: curl -X POST 
  https://restful-booker.herokuapp.com/booking 
  -H 'Content-Type: application/json' 
  -d '{
    "firstname" : "Jim",
    "lastname" : "Brown",
    "totalprice" : 111,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}'

﻿

Request Headers
Content-Type
application/json
Body
raw (json)
json
{
    "firstname" : "Jim",
    "lastname" : "Brown",
    "totalprice" : 111,
    "depositpaid" : ,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}
DELETE
Verify the response while deleting the bookings with valid ID
https://restful-booker.herokuapp.com/booking/9532
Generated from cURL: curl -X DELETE 
  https://restful-booker.herokuapp.com/booking/1 
  -H 'Content-Type: application/json' 
  -H 'Authorization: {{vault:basic-auth}}'

﻿

Authorization
Basic Auth
Username
<username>
Password
{{vault:authorization-password}}
Request Headers
Content-Type
application/json
Authorization
{{vault:basic-auth}}
GET
Check the booking is deleted by using !D
{{base_url}}/booking/{{bookingid}}
Generated from cURL: curl -i https://restful-booker.herokuapp.com/booking/1﻿

﻿

