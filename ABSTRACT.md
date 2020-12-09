# Woodchuckin’: Predicting An Early Spring with RedisAI

Groundhog. Woodchuck. Whistlepig. Regardless of what you call this marmot, there’s an important question we ask it every year—will there be six more weeks of winter? Normally, we have to go to Pennsylvania for our answer. There, in the borough of Punxsutawney dwells a groundhog named Phil and a group called the Groundhog Club. On February 2nd, the president of the Groundhog Club speaks with Phil in his native language of Groundhogese and—in his woodchuck whispering ways—asks if Phil has seen his shadow. If he has, six more weeks of winter. If not, an early spring!

However, this bucolic event is not without its controversy. The fine folks at the People for the Ethical Treatment of Animals have objected to it, claiming that the rigors of the event causes Phil undue stress. And, they have suggested replacing Phil with a robotic groundhog. Well, that’s exactly what we are going to do in this talk... with data science!

The brain of our electronic whistlepig is a simple machine learning model that predicts if Phil would see his shadow—based on his location and recent weather information. We’ll deploy this model to RedisAI, showing how to host models in a way that provides abstractions for both the data scientists and the software developers who respectively make and consume models. And, we’ll host some of the data needed to make the prediction in Redis itself, demonstrating how data locality improves model performance and helps our cybernetic woodchuck chuck more wood.

When the talk has ended and the woodchuckin’s done, we’ll have a working application that tells us what to expect this spring and the knowledge to apply Redis to other AI problems, giving us easier abstractions and faster predictions.
