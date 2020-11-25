# machine-learning-challenge

I created two models for classifying exoplanet detection as confirmed, candidate, or false positives from the given Kepler data.

From my interpretation of the documentation, the false positive flags included in the data cannot be used in modeling, as these are directly related to what we are trying to predict (i.e. the false positive flags cause the detection to be classified as false positive 100% of the time). The challenge is to create our own false positive flag from the measurement data.

I used a random forest technique to focus on the most important quantities in the data for predicting false positives. I know from my experience as a scientist that errors in certain quantities often scale with the quantities themselves, so I would only choose the quantity highest on the importance list pertaining to any measurement. For example, I included koi_prad but not koi_prad_err1 when creating models, because koi_prad was highest on the list of importance determined by my random forest analysis.

My final submission is my k nearest neighbors model, which I tuned up to 68.5% accuracy. I was hoping for more accuracy, but I was happy to achieve this at least. 

My second classifier was a support vector machine. This turned out to be less accurate than k nearest neighbors, but with a couple rounds of GridSearch I tuned in to some parameters that yielded 64.5% accuracy.

For higher accuracy, I imagine I would need to use some model based on neural networks, which unfortunately I did not have time to experiment with this time around. This was a great project to build up my curiosity in exploring further.