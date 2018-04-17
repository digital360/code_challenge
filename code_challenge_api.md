         _ _       _ _        _ _____  __    ___  
      __| (_) __ _(_) |_ __ _| |___ / / /_  / _ \
     / _` | |/ _` | | __/ _` | | |_ \| '_ \| | | |
    | (_| | | (_| | | || (_| | |___) | (_) | |_| |
     \__,_|_|\__, |_|\__\__,_|_|____/ \___/ \___/ 
             |___/ a𐧻p𐧻i𐧻𐧻c𐧻h𐧻a𐧻l𐧻l𐧻e𐧻n𐧻g𐧻e𐧻𐧻              

# Technical evaluation
The purpose of this evaluation is to determine not only
what you've produced at the end of the day but also how
you produced it and what you understood about the current
technical architecture.

The ultimate goal of the API (and overall product) is
to get it out of the hands of engineering as much as possible,
please consider this vision when architecting the solution.

Please read through this document thoroughly and feel free
to ask any questions along the way.

## The challenge
The challenge is to implement a new formatter within the existing
API. A general breakdown of the steps that you'll need to carry
out are as follows:

- Find out where the formatter is located
- Implement a new formatter by looking at the existing codebase
- Analyse our composer file and gain an understading from a high level
around why we'd do it this way instead of other types of methods

### API routes
```
http://{{host}}/v1/php-test/endpoint1
```

### Expected request
```
http://{{host}}/v1/php-test/endpoint1?format=founded_year:decimal0,upper,currency3|thousands,address:lower
```

### Expected response
```
{
   "data":[
      {
         "company":"GOOGLE INC",
         "revenue":"$ 5,438,997,819.433",
         "founded_year":"1998",
         "address":"menlo park, california, united states"
      }
   ],
   "meta":{
      "pagination":{
         "total":1,
         "count":1,
         "per_page":15,
         "current_page":1,
         "total_pages":1,
         "links":[

         ]
      }
   }
}
```

### Acceptance criteria
To be successfully evaluated, the team at Digital360 must
have the following:

- At least something coded by the end of the session
- What your understanding is of the existing API architecture
- How you extended the existing codebase
- How your solution impacted performance
- An idea of what you could improve if you had more time

#### Bonus round
Bonus points will be given to those who can also find time
to optimise their code as they're moving through this
challenge.

## Team at your disposal
You have the entire technology team at your disposal, if
you're conducting this evaluation during a working week, use
the team to your advantage.

## Running the API
From the root directory run:
```
$ ./build dev
```

### Authentication
To authenticate, run the following POST request:
```
http://{host}/v1/auth/logon
```

Along with the following JSON body:
```
{
    "email": "{supplied at interview time}",
    "password": "{supplied at interview time}"
}
```

The response will contain the auth token. Get the auth token
and pass that with any following requests in the header as a
Bearer Token.
