         _ _       _ _        _ _____  __    ___  
      __| (_) __ _(_) |_ __ _| |___ / / /_  / _ \ 
     / _` | |/ _` | | __/ _` | | |_ \| '_ \| | | |
    | (_| | | (_| | | || (_| | |___) | (_) | |_| |
     \__,_|_|\__, |_|\__\__,_|_|____/ \___/ \___/ 
             |___/ a𐧻p𐧻p𐧻𐧻c𐧻h𐧻a𐧻l𐧻l𐧻e𐧻n𐧻g𐧻e𐧻𐧻              

# Technical Evaluation
The purpose of this evaluation is to determine not only
what you've produced at the end of the day but also how
you produced it and what you understood about the current
technical architecture.

The ultimate goal of the application (and overall product) is
to get it out of the hands of engineering as much as possible,
please consider this vision when architecting the solution.

Please read through this document thoroughly and feel free
to ask any questions along the way.

## Team at your disposal
You have the entire technology team at your disposal, if
you're conducting this evaluation during a working week, use
the team to your advantage.

## The challenges
The challenges are broken up into 2 pieces in which the team at
Digital360 will advise which path you must take.

### Challenge #1
This challenge is to replicate an existing module that we use
to display visual metrics and one that we use to capture data.
What we want to see, apart from the way you've coded those
modules, is also how you think this could be done better from
an architectural perspective.

We want you to replicate our current [Digital Marketing Overview](http://localhost:8080/digital/digital-marketing/overview)
module, and our current [Financial Central](http://localhost:8080/advisory/financial-central)
module.

#### Acceptance criteria
To be successfully evaluated, the team at Digital360 must
have the following:

- At least something coded by the end of the session
- The ability to explain what you've produced, line by line
- An idea of what you could improve if you had more time
- The ability to explain how the architecture can improve
- Commits; we want to see your commit history (you can use
git on the command line or pre-installed SourceTree).

#### Running the application
To run the application, simply do the following in bash:
```
$ npm run dev -- https://test.api.engineroom.com.au/v1/
```

#### Folder structure
The code is located in `~/Tests/engineroom`.

The folder structure for the project is laid out very similar
to the UI navigation to make finding things a little easier
given the current architecture.

Your focus source folders/files will be as per the following:
    
    .
    +-- src
    |   +-- pages
    |   |   +-- digital
    |   |   |   +-- Index.vue
    |   |   +-- advisory
    |   |   |   +-- financial-central
    |   |   |   |   +-- Index.vue
    |   +-- components
    |   |   +-- data-rendering
    |   |   |   +-- *
    |   |   +-- forms
    |   |   |   +-- *

---

### Challenge #2
We have a couple of data API endpoints to display an
Area and Pie chart, and another endpoint to facilitate a form
for saving data. Your challenge is to come up with architecture
to not only facilitate these requests, but also to promote
scalability and re-usability.

Frameworks and UI are not important, and will not be the focal
points of discussion or markings. Choose whichever framework
is best for the task at hand (if any at all) and if you
are confident have a crack at the UI.

Some considerations for scalability are:
- The application shouldn't depend on the backend to function
- The application should be able to adapt to changing data
structures

#### Acceptance criteria
To be successfully evaluated, the team at Digital360 must
have the following:

- At least something coded by the end of the session
- The ability to explain what you've produced, line by line
- An opinionated view on your architectural decision
- How you think this architecture is scalable and re-usable
- How you think you could further optimise the codebase given
you had more time

#### Charts
Use whatever is easiest to display the following charts, remember
UI is not a deciding factor. Consider the following when
architecting this solution:
- Can the data structure be dynamic?

##### Area Chart (GET)
```
https://test.api.engineroom.com.au/v1/modules/592fd0dc1b0f3d006c58714a/data/get-look-data?filter=looker_id:313|from_date:2017-02-19|to_date:2018-02-19|business:59cb5428794a4c0456100b82
```

##### Pie Chart (GET)
```
https://test.api.engineroom.com.au/v1/modules/592fd0dc1b0f3d006c58714a/data/get-look-data?filter=looker_id:316|from_date:2017-02-19|to_date:2018-02-19|business:59cb5428794a4c0456100b82
```

#### Form
Besides the form having to capture information, we'd like to
see the current stored 'form data' in a table. The ability
to edit/delete existing stored 'form data' would be considered
bonus points.

Consider the following when architecting this solution:
- Can the form elements be more dynamic?

##### Existing form data (GET)
```
https://test.api.engineroom.com.au/v1/modules/59ac0372d28e0a00ef5bc052/forms/59ac0372d28e0a00ef5bc055/items?filter=business:59cb5428794a4c0456100b82&with=file,business,category,document_type
```

##### Storing form data (POST)
```
https://test.api.engineroom.com.au/v1/modules/59ac0372d28e0a00ef5bc052/forms/59ac0372d28e0a00ef5bc055/items?filter=business:59cb5428794a4c0456100b82
```

> Payload
```
{
   "business_id":"59cb5428794a4c0456100b82",
   "comment":"This is a test comment",
   "file_id":"5ad55debaeef4f046c03f532",
   "document_type_id":"59d17196794a4c06a9712542",
   "business_confirmation_id":"59cb5428794a4c0456100b82",
   "category_id":"59d1717e794a4c0676201942",
   "file_name":"Test"
}
```
