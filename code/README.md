# Woodchuckin': Predicting An Early Spring with RedisAI

This codebase contains the data and Jupyter Notebooks to make a model that predicts if a groundhog in your area will see his shadow given the temperature forecasted for February and March (i.e six more weeks). And who doesn't want to do that. It uses the data spanning the last 125 years from the event Punxsutawney, Pennsylvania—made famous by the movie Groundhog Day—and the NOAA. With it, you can build a model that predicts 'Full Shadow' or 'No Shadow' for any climatic region where groundhogs are found.

## Start Redis

We're using RedisAI and RedisGears to do this magic. The easiest way to get this running is to use the `start-redis.sh` script. This script is really simple, open it up and take a look. If you're a Windows user, it should be easy to make a script that does the same thing there. And if you do send me a pull request!

Regardless, this script makes use of Docker, so make sure you have that installed and running first. Then, it's just a matter of running it:

    $ ./start-redis

And that's it.

## Setting Stuff Up

All the code is in Python in Jupyter Notebooks. You'll need to install Python so go and download that if you need to. I used version 3.8 but I'm sure other versions will work well too.

First, setup a virtual environment for Python:

    $ python3 -m venv venv

And then activate that environment:

    $ source venv/bin/activate

And then install all the dependencies (including Jupyter):

    $ pip install -r requirements.txt

And then start up the notebooks:

    $ jupyter notebook

## The Notebooks

The notebooks are, like all good code &lt;sarcasm&gt;self documenting&lt;/sarcasm&gt;. There are three of them and the serve the following purposes:

  1. **Data Preparation**: Takes the raw data and turns it into data we can use. Part of this involves building some intermediate models to impute values for our final dataset.
  2. **Model Building**: Takes the data from the first notebook and uses it to make the model that will predict groundhog shadows.
  3. **Using RedisAI**: Places the model in Redis and tries it out.
  4. **Data Locality**: Loads the forecast data needed to make predictions in Redis and uses RedisGears to trigger predictions using that reference data and a latitude and longitude provided by the user.

If you just want to see it all work, run the notesbooks front to back in order.

## Making Predictions

This can be done with `redis-cli`. Just use the RG.TRIGGER command, the event you want to trigger, and the latitude and longitude. For example, here's the prediction for Punxsutawney, Pennsylvania:

    > RG.TRIGGER woodchuckin 40.9437 -78.9709

And you should get back a simple response of:

    1) "Full Shadow"

And that's it., We're all done. This could easily be incorporated into an application. Just grab the latitude and longitude from a mobile device, browser, or plain old user input; call some sort of REST, gRPC, GraphQL thing; and have that call Redis.
