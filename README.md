# A Medication Compliance Monitoring System using Machine Learning and Distributed Computing
By: Katja Wittfoth, Hai Vu Le, Donya Fozoonmayeh and Diane Woodbridge
<br>

This is a research project in cooperation with professor Diane Woodbridge at University of San Francisco.
My team and I presented our project's result at the [Data Institute SF Conference 2019](https://www.sfdatainstitute.org/). We have submitted a scientific paper which is currently in review. Our work is built upon and continuation of the [project](https://www.ncbi.nlm.nih.gov/pubmed/30441452) which was published Jul 2018.

<p align="center">
    <img src="/images/smartwatch.png", align="middle" width=700"> 
</p>

## Research Overview
This research aims to detect medication intake based on accelerometer and gyroscope
data collected by smartwatches. The end goal is to develop a smart machine learning
application that would provide patients with accurate and timely
reminders to improve their medication adherence.

## Why medication compliance is important?
Poor medication intake threatens a patient's health and puts an economic burden on the health-care system. The annual medication-adherence rate in the US is between 25% to 50% which accounts for about $300 billion avoidable healthcare costs.

## Data processing and engineering
We collected three-dimensional sensor data of
following activities: medication intake (pill and liquid),
texting, writing, drinking bottled water, and walking. 
The data is from 24 study subjects using LG Watch Sport
devices.
To account for the variation in activity duration and
the difference in subjects' pace, all records were
discretized into the same number of time windows.
For each dimension, we extract 18 descriptive
statistics out of each window as features to
train ML models.

To tackle the challenge of processing massive high frequency
sensor data in real time, we take a distributed computing approach with an end-to-end
pipeline built on distributed systems.

<br>

<p align="center">
    <img src="/images/pipeline.png", align="middle" width=700"> 
</p>

## Results
For efficient medication adherence application, it is important to have
an algorithm which would not only yield highest precision but also would be cost-efficient in production meaning fast training and prediction time.

We trained various ML models
for this classification problem, including Logistic
Regression, Random Forest, and XGBoost. Our best RF model yields a precision score of 0.98
with data discretized into 40 windows. It
outperformed other models in terms of speed with 14 seconds training and 0.17
seconds prediction time.

## Tools
Python, PySpark, SparkML, MongoDB, AWS S3, AWS EMR  
<br>
*This repository is a duplication of the private repository with confidential contents removed.*
