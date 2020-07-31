# api-interview-question-spacex


spacexdata.com provides an API to query attributes about SpaceX launches (https://github.com/r-spacex/SpaceX-API/blob/master/docs/v4/README.md). For this exercise we are going to be working with two resources in particular:
1) https://github.com/r-spacex/SpaceX-API/blob/master/docs/v4/starlink/schema.md
  Some relevant fields to note in the reponse:
    - spaceTrack --> CREATION_DATE
    - longitude
    - latitude
    - launch


    For the purposes of this exercise, let's assume that the CREATION_DATE field is the date that the starlink satellite was at the given latitude/longitude

2) https://github.com/r-spacex/SpaceX-API/blob/master/docs/v4/launches/schema.md

The Problem:
We want to have an *hourly* record of the starlink satellite locations (latitude, longitude). We want to be able to query a database to answer the question "Where is the latitude/longitude Starlink satellites for launch <launch id> on the date <some date here>?"

The Task:

1) Create a task(s) to import the API results for 'launches' and 'starlink' data into a database. Keep in mind that you'll need to keep track of 'starlink' longitude/latitude over time, as described in the 'Problem' section. If we were to put this in production, we'd potentially put it behind a scheduler task, but for the purposes of this task, we will just assume that it's runnable from a python shell.

  To complete this task, your code will need to be able to insert rows into a database (of your choice!) Feel free to model it however you choose
  
  Bonus:
    - Tests. Feel free to test what you think needs testing, and ignoring what you think doesn't need it
    - Setup the database and task in a docker compose container so that we can run it on our end, as well


2) Write a method Get_All_Starlinks that accepts (<launch_id>, <date_time>) and returns all the starlink satellite positions for that given point in time

Example:
launch_id = "5eb87d30ffd86e000604b378"
date_time = "2020-07-30 18:17:33"

Get_All_Starlinks(launch_id, date_time)
should give me back a list of objects (JSON, or Python objects...whichever is most convenient!) representing the starlink satellite positions at that <date_time> for the given <launch_id>



Don't spend more than 2 hours on this exercise. If you hit two hours and haven't finished, that's totally fine! In that case, just wrap up with some final thoughts about what you'd do to improve the code, and what you'd like to test (and what you think isn't worth testing as well!)
