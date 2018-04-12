         _ _       _ _        _ _____  __    ___  
      __| (_) __ _(_) |_ __ _| |___ / / /_  / _ \ 
     / _` | |/ _` | | __/ _` | | |_ \| '_ \| | | |
    | (_| | | (_| | | || (_| | |___) | (_) | |_| |
     \__,_|_|\__, |_|\__\__,_|_|____/ \___/ \___/ 
             |___/ j𐧻s𐧻𐧻c𐧻h𐧻a𐧻l𐧻l𐧻e𐧻n𐧻g𐧻e𐧻𐧻              

# Technical Evaluation
The purpose of this evaluation is to determine not only
what you've produced at the end of the day but also how
you produced it and what you understood about the current
technical architecture.

## The challenge
The challenge is to replicate an existing module that we use
to display visual metrics and one that we use to capture data.
What we want to see, apart from the way you've coded those
modules, is also how you think this could be done better from
an architectural perspective.

We want you to replicate our current [Digital Marketing Overview](http://localhost:8080/digital/digital-marketing/overview)
module, and our current [Financial Central](http://localhost:8080/advisory/financial-central)
module.

### Requirements
To be successfully evaluated, the team at Digital360 must
have the following:

- At least something coded by the end of the session
- The ability to explain what you've produced, line by line
- An idea of what you could improve if you had more time
- The ability to explain how the architecture can improve
- Commits; we want to see your commit history (you can use
git on the command line or pre-installed SourceTree).

## Team at your disposal
You have the entire technology team at your disposal, if
you're conducting this evaluation during a working week, use
the team to your advantage.

## Running the application
To run the application, simply do the following in bash:
```
$ npm run dev -- https://test.api.engineroom.com.au/v1/
```

### Folder structure
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

Decide the structure you want for the new modules and place them
where you see fit.





Feedback - 
Question was not clear, it shouold be more geared towards not replilcation rather
the thought process
