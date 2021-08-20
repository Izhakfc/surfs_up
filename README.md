# surfs_up
## Overview of the analysis: 
Climate Analysis and Data Exploration of Climate Database Using Python (Pandas, Matplotlib), SQLAlchemy (ORM Queries) and Flask of the city of Oahu, Hawaii in order to see if there are proper conditions to open a surfing and ice cream store.
## Results: 
### STEP 1: Climate Analysis and Exploration
Using Python nd SQLAlchemy a basic climate analysis and exploration of the data of the climate database. The following analysis was performed:
#### Precipitation Analysis
* Design a query to retrieve the precipitation data of the last year and displaying only <code>date</code> and <code>prcp</code> values.
* Store the query in a pandas dataframe, set the index as the date column and sort the values by date.
* Use Matplotlib to plot the data from the pandas dataframe.
* Use the <code>describe()</code> method to  obtain the summary statistic for the precipitation data.
#### Station Analysis
* Design a query to obtain how many <code>stations</code> were available in the analysis.
  * List the stations and the number of observations in descending order.
  * Obtain the station with the highest number of observations.
* Using the data from the highest performing station obtain:
  * The <code>lowest temperature</code> recorded.
  * The <code>highest temperature</code> recorded.
  * The <code>average temperature</code> recorded.
  * Retrieve the last 12 months of tobs (Temperature Observations) and plot the results in a histogram.

### STEP 2: Climate App
#### Hawaii Climate App (Flask API)
Design a Flask API based on the queires that have been developed in the previous step.
##### Setting up Flask
Adding the neccesary code to start developing a web application with flask

        from flask import Flask, jsonify
        app = Flask(__name__)
        (----- YOUR ROUTES -----)
        if __name__ == '__main__':
           app.run(debug=True)
           
##### Adding Routes
The next routes were defined in order to display different results from th eprevious step, the routes were:
* The welcome route: <code>@app.route("/")</code>
  * A welcome route that displays the title and the available routes of our web app.
  * ---Image---
* The precipitation route: <code>@app.route("/api/v1.0/precipitation")</code>
  * Convert the query results to a dictionary using <code>date</code> as a key and <code>prcp</code> as a value.
  * Return the JSON file of the dictionary. 
* The stations route: <code>@app.route("/api/v1.0/stations")</code>
  * Return a JSON list containing the stations of the database.
* The mothly temperature route: <code>@app.route("/api/v1.0/tobs")</code>
  * Query the dates and tobs from last year.
  * Return a JSON list of tobs for the las year. 
* The measurements of central tendency route: <code>@app.route("/api/v1.0/temp/start")</code> and <code>@app.route("/api/v1.0/temp/start/end")</code>
 * Query a list of the minimun, maximum and average temperatures of a given <code>start</code> and <code>end</code> date.
 * If no end date was provided, it will return the results of any available date greater than or equal than the starting date.
## Challenge

## Summary: 
Provide a high-level summary of the results and two additional queries that you would perform to gather more weather data for June and December.
