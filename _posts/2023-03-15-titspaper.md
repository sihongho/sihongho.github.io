---
layout: post
title: Data-Driven Distributionally Robust Electric Vehicle Balancing for Autonomous Mobility-on-Demand Systems under Demand and Supply Uncertaintiess
date: 2023-03-15 15:09:00
description: 
tags: research
categories: AMoD
---

`We are happly to introduce our recent publication on IEEE Transactions on Intelligent Transportation Systems (TITS):`

### "Data-Driven Distributionally Robust Electric Vehicle Balancing for Autonomous Mobility-on-Demand Systems under Demand and Supply Uncertainties"

<div class="publications">

{% bibliography -f papers -q @*[key=he2023data_tits]* %}

</div>

### Abstract
Electric vehicles (EVs) are being rapidly adopted due to their economic and societal benefits. Autonomous mobility-on-demand (AMoD) systems also embrace this trend. However, the long charging time and high recharging frequency of EVs pose challenges to efficiently managing EV AMoD systems. The complicated dynamic charging and mobility process of EV AMoD systems makes the demand and supply uncertainties significant when designing vehicle balancing algorithms. **In this work, we design a data-driven distributionally robust optimization (DRO) approach to balance EVs for both the mobility service and the charging process.** The optimization goal is to minimize the worst-case expected cost under both passenger mobility demand uncertainties and EV supply uncertainties. **We then propose a novel distributional uncertainty sets construction algorithm that guarantees the produced parameters are contained in desired confidence regions with a given probability.** To solve the proposed DRO AMoD EV balancing problem, **we derive an equivalent computationally tractable convex optimization problem**. Based on real-world EV data of a taxi system, we show that with our solution the average total balancing cost is reduced by 14.49%, and the average mobility fairness and charging fairness are improved by 15.78% and 34.51%, respectively, compared to solutions that do not consider uncertainties.

### What is an Autonomous Mobility-on-Demand System?

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/project_tits2023/amod.gif" title="https://www.youtube.com/watch?v=4B7mZFU2sB4" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

In Autonomous Mobility-on-Demand (AMoD) systems, **self-driving** vehicles provide personal on-demand transportation service for customers and rebalance themselves to maintain acceptable quality of service throughout the system. AMoD systems have been advocated as one of the most promising energy-efficient transportation solutions. What's more, electric vehicle AMoD systems directly address the problems of oil dependency and air pollution.

### Motivations

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/project_tits2023/fig3.jpg" title="motivation image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The above figure is a heat map of passenger demand in Shenzhen city. It shows the unbalanced distribution of mobility demand. There is higher passenger demand in downtown and airport areas than in suburban areas. This realistic situation verifies the necessity to provide fair service in EV AMoD systems. These blue markers denote charging station locations. The unbalanced charging stations distribution also enhances our motivation to consider charging fairness in EV AMoD balancing problems.

However, most existing vehicle allocation methods and charging scheduling approaches **do not consider uncertainties** by assuming the measurement and prediction models are perfect, **while model uncertainty affects the performance of decisions**. And it is difficult to accurately predict passengers’ demand and EVs’ charging patterns. As the promotion of EVs continues, **we cannot ignore the uncertainties caused by EVs’ charging behaviors**.

### Contributions

- To the best of our knowledge, our proposed mathematical system-level vehicle balancing framework is the first to consider both future mobility demand uncertainties and EV supply uncertainties for EV AMoD systems. While model predictive control algorithms have been designed considering AMoD system demand uncertainties in the literature, the supply side uncertainties for EV AMoD are not well studied yet.

- We design a distributionally robust optimization approach to balance EVs across a city to provide fair passenger mobility and EV charging service while reducing the total balancing cost. We consider probabilistic distribution uncertainties of both the passenger mobility demand and the EV supply caused by the challenge of charging process prediction. The proposed problem formulation decouples the mutual dependencies between EV supply and passenger demand. We further design an efficient algorithm to construct distributional uncertainty sets, and prove that the produced uncertainty set parameters are guaranteed being contained in desired confidence regions with a given probability.

- We derive an equivalent convex optimization problem for the proposed distributionally robust optimization problem. Hence, we provide a system-level performance guarantee in a computationally tractable way under supply and demand uncertainties. Based on the E-taxi fleet of Shenzhen city, which is a real-world EV AMoD system dataset, we show that our method reduces the average total balancing cost, the average mobility unfairness and charging unfairness by 14.49%, 15.78% and 34.51%, respectively, compared to non-robust solutions.

### Framework Structure

<!-- <div align="center">
<img src="/assets/img/project_tits2023/fig1.png"  width="90%" height="90%">
</div> -->

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/project_tits2023/fig1.png" title="motivation image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

In **module 1**, we use historical data to train a prediction model for supply and demand then use the well-trained prediction models as the input of our Algorithm 1 to finally get the distributional uncertainty sets for demand and supply in form of equation (20) in the paper. In **module 2**, we get the DRO EV balancing problem (the distributionally robust optimization problem (12) in the paper) using the real-time sensing data and distributional uncertainty sets. In **module 3**, we apply the conclusions in the derived Theorem 1 to obtain the EV balancing decisions by solving the equivalent convex optimization problem (25) in the paper.

### Real-World E-Taxi Data

We evaluate the performance of the designed distributionally robust optimization-based EV balancing method with electric taxi (e-taxi) data from the Chinese city Shenzhen (one of the largest cities in China, which operates over 10,000 E-taxis). The used data includes **60GB EV GPS data, and 5.5 GB transaction data from over 10,000 EVs**. There are four different datasets used in this paper, including E-taxi GPS data (vehicle ID, locations, time and speed, etc), Transaction data (vehicle ID, pick-up and drop-off time, pick-up and drop-off location, travel distance, etc), charging station data (locations, name, the number of charging ports, etc), and city partition data (geographic boundaries of 491 small separate regions composing Shenzhen). Our datasets are obtained by collaborating with the Shenzhen Transportation Committee for its smart city initiative. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/project_tits2023/data.png" title="data image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Experimental Results

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/project_tits2023/fig8.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/project_tits2023/fig9.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/project_tits2023/fig10.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The **total balacning cost** of our method is lower than that of the two baseline methods. In particular, the average total balancing cost is reduced by 14.49% compared with the non-robust method and reduced by 7.37% compared with the baseline robust method. 

By using our DRO method, the average **mobility fairness** and **charging fairness** are improved by 15.78% and 34.51%, respectively, compared to the non-robust method, and improved by 10.45% and 30.92%, respectively, compared to the baseline robust method. 

Our DRO method outperforms the non-robust method because it considers both supply and demand uncertainties when making EV balancing decisions. The DRO problem formulation, uncertainty set construction based on data and equivalent convex optimization form derivation procedures are all designed carefully to solve the challenge in a computationally tractable way. In contrast, the baseline methods in the literature either do not consider model uncertainties such as the non-robust methods, or only consider one type of uncertainty such as the robust optimization method with the demand uncertainty.


`You may also be interested in our related publications on IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS), AI4ABM Workshop at the International Conference on Learning Representations (ICLR) 2023 and ACM Transactions on Cyber-Physical Systems (TCPS):`

<div class="publications">

{% bibliography -f papers -q @*[key=he2020data_iros]* %}

{% bibliography -f papers -q @*[key=he2023robust_iros_uncertain_state]* %}

{% bibliography -f papers -q @*[key=he2023robust_iros_uncertain_model]* %}

{% bibliography -f papers -q @*[key=he2023robust_ev_ai4abm]* %}

{% bibliography -f papers -q @*[key=miao2021data_tcps]* %}
</div>
