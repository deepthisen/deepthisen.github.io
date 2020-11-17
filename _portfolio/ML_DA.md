---
title: "Machine Learning and Data Analytics in Petroleum Reservoir Engineering"
excerpt: "Deriving meaningful insights from oilfield data using statistical methods a.k.a my PhD research."
collection: portfolio
---

## Data-Driven Rate Optimization Under Geologic Uncertainty 

The most crucial decisions while operating an oilfield happens pertains to 

a. At what rate should an operator extract oil from producer wells

b. At what rate should water be injected into the reservoir to push out maximum oil from the producer wells in (a.)

c. When/Where/Whether to drill the next well

The answers to all these questions are fairly elusive to the reservoir engineer owing not only to the uncertainty in the subsurface geology, but also a range on operational constraints that are required for safe operation. Moreover, in order to account for all the uncertain variables and constraints, one has to run a computationally-costly simulation a gazillion times.  

My primary research focuses on solving some of these problems by invoking machine-learning at the simulation step. Specifically, I try to predict some aspects of the subsurface flow pattern, without having to run the costly simulation. It turns out that the machine-learning model runs faster than the simulation by around 3 orders of magnitude; so accounting for multiple variables, scenarios etc. becomes a breeze.

The first part of the work was presented at SPE-ATCE.  

<center>
  <img src="/images/Picture1.png" alt="drawing" width="800"/>
</center>


## Using RNNs to Understand Reservoir Connectivity

In case we do not have a geologic model on which we can run the simulator, but have access to a lot of historical data (rates and pressures at operational wells in the field), we can use machine-learning based approaches to understand certain key aspects of the reservoir. One way to do this is to fit a recurrent neural net to the history and study the variable importance of each input (in this case, the injection rates) to each output (the production rates). However, the feasibility of such an approach is debated due to a number of reasons:

a. This approach needs historical data that ideally covers the entire space of possible inputs and underlying physics. This tends to be a major problem in reservoir engineering, wherein we have hundreds of wells, yet only a few years of data.

b. The RNN architecture and training (loss function formulation, window selection etc.) has to capture complex non-linear relationship between input and output. This problem is compounded by the fact that the underlying physics is generally not time-invariant. However, the approach is still worth a shot, given we have sufficient data and the physical regime does not change too much in the space where we make the predictions.

<center>
  <img src="/images/rnn_workflow.png" alt="drawing" width="1300"/>
</center>


The real value in training an RNN in such a case, would be to infer the connectivity between injectors and producers in the field. This may be measured in terms of the 'permutation-based variable importance', where one measures the deviation in the prediction from the true output on shuffling the columns of the inputs. In order to validate such an approach one must clearly define what measure of 'connectivity' that is being learned by the RNN. For starters, I compared the average flux from the injectors to producers with the variable importance I computed using the RNN.

<center>
  <img src="/images/rnn_VI_comparison.png" alt="drawing" width="500"/>
</center>


## Time-Series Clustering Applications to Petrophysics  

One of the more established applications of machine-learning in oil and gas would be in the realm of well-log and seismic interpretation. I had the opportunity to work as summer intern with the data science team at TGS-NOPEC, where they specialize in machine-learning applications in the petrophysics/geophysics space. Working with the team was a great learning opportunity for me  and I was able to develop an unsupervised approach for anomaly detection in density logs. 


## Capacitance-Resistance Models 


