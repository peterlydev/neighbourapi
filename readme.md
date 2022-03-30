# Neighbour API Quick Start

## Overview
--- 
This API is a neighbourhood collaboration site and this system is designed to keep track of people, houses, and addresses of those houses. These include the following:

* Each person has a name, age and number of people in their household
* Each house has an address and an owner
* Each address has a postcode and street address

The API enables users to

* Store people, houses and addresses
* Look up a house, its address and owner
* Look up people in our neighbourhood within certain age brackets and with specific household sizes

This will represent data in a NoSQL format as it's in objects.

## Neighbour API
---
```
$ curl; https://api.neighbourhoodapi.com/

Your friendly neighbourhood
``` 

---
The following response will return a list of people within the neighbour from the SQL database:

```
GET /people
$ curl https://api.neighbourhoodapi.com/people

[{
    "id": 1,
    "firstName": "Sidar",
    "lastName": "Ozbek",
    "age": 25,
    "numOfPeople": 3
},

{
    "id": 2,
    "firstName": "Jaxsan",
    "lastName": "Sivanesan",
    "age": 22,
    "numOfPeople": 5
}] 

```

This will represent a status report of 200.

---

In order to specifically get the information of one person, you may do the following:

```
GET /people/:firstName/
$ curl https://api.neighbourhoodapi.com/people/jaxsan
{
    "id": 2,
    "firstName": "Jaxsan",
    "lastName": "Sivanesan",
    "age": 22,
    "numOfPeople": 5
}
```
Below is an example of where you can do an advanced search of a particular person along with their age and how many people live in their household.

```
GET /people
$ curl https://api.neighbourhoodapi.com/people?age=20-30&numOfPeople=3/

{
    "id": 1,
    "firstName": "Sidar",
    "lastName": "Ozbek",
    "age": 25,
    "numOfPeople": 3
}

```

So now you know how to look up the people within your neighbourhood, now it's time to view the house and the owner. 

```
GET /house/
$ curl https://api.neighbourhoodapi.com/house/
[{
    "id": 1,
    "address": "12 Ha-Ha Road SE6 5TG",
    "owner": "Marcus Albrighton"
},

{
    "id": 2,
    "address": "13 Strawberry House NW6 6RG",
    "owner": "Billy Usman"
}]
```
---
Now it's time to specifically view an owner of a house

```
GET /house/:owner
$ curl https://api.neighbourhoodapi.com/house/billyusman
{
    "id": 2,
    "address": "13 Strawberry House NW6 6RG",
    "owner": "Billy Usman"
}
```

All of the above will represent a status report of 200 meaning that the content exists







