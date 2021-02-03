# Blue Onion Labs Take Home Test

Hey! We are stoked that you are interested in joining the team at Blue Onion Labs.

We have crafted the following test to see how you approach pulling and manipulating of data. We want to get a general idea of how you approach some common types of problems that we encounter here at Blue Onion (we are really proficient at integrations!). There is mention of Ruby/Python libraries in the notes, but feel free to use whatever backend code/framework that you like! For the frontend, React would be ideal.

## Background
[spacexdata.com](https://docs.spacexdata.com/) provides an API to query attributes about SpaceX launches (https://github.com/r-spacex/SpaceX-API/blob/master/docs/v4/README.md). For this exercise we are going to be working with one resource in particular:
- The [Starlink Schema](https://github.com/r-spacex/SpaceX-API/blob/master/docs/v4/starlink/schema.md)
  Some relevant fields to note in the reponse:
    - longitude
    - latitude

## The Problem:
We want to be able to import the SpaceX Satellite data, and then we want to find out which satellites are physically closest to a given point.

## The Task (Part 1):
Create a runnable script to import the API results for 'starlink' data into memory. Have the script accept the following arguments:
- latitude
- longitude
- an integer N

The script should return the first 'N' number of satellites which are *closest in physical distance* to the input latitude/longitude. We essentially want to be able to ingest the satellite data, then find out which one is closest to a given point at any given time. Do not worry about going deep into the math of distances between points on the ground and space in terms of lat/lon. You can assume the satellite positions (in lat/lon) and the position we compare it to are at the same altitude. No need to be too exact with this one :)
You will find the following package(s) useful:
    
  - For Python: https://github.com/mapado/haversine
  - For Ruby: https://github.com/kristianmandrup/haversine

## The Task (Part 2):
Put this logic into a webserver and put it behind an endpoint. Feel free to use whatever framework you're most comfortable with.

The endpoint should accept an integer parameter 'N' (as a query param or in the body) to pass to the logic from 'Part 1'
The endpoint should return JSON that is an array of longitude/latitude points.

## The Task (Part 3):
This is the fun part! Plot those points on an interactive globe. Don't worry, there is a library to do the heavy lifting here: https://github.com/chrisrzhou/react-globe

To do this we'll want to:
  - Create a super lightweight React app (create-react-app or any other generators are fine).
  - Import the react-globe library https://github.com/chrisrzhou/react-globe
  - From the client app, call the endopint from 'Part 2' and display those points on the react-globe. With whatever number N you feel like.

After this, you're done! No need for the code to be perfect. If you have thoughts about how things could be better, just make notes/comments as you go. Given the time constraint, the quality of the code isn't the most important thing.


*Bonus points*:
- Tests. Feel free to test (or just make notes about) what you think needs testing, and make a note of what you think doesn't need any testing (and why!)

### How to Submit

1. Run through it one last time to make sure it works!
2. Push up to your repo one last time (or save your working directory to a 'zip')
3. Reach out to us with your solution

### Questions

If you have any questions at all during the challenge do not hesitate to reach out! Whether it be a question about the requirements, submitting, anything, just send us a note!
