---
layout: post
title:  "Forecasting cryptocurrency prices using high-frequency data"
date:   2018-12-27 09:13:20 +0100
categories: jekyll update
---
A good cryptocurrency forecasting model that has worked for me is taking linear combinations of technical indicators. The technical indicators represent the momenta of market-microstructure effects - order imbalance, trend-following, etc. It’s lightweight and not computationally intensive so it can be run on cheap hardware. 

A future price of a cryptocurrency is computed using the current price plus the summation of weighted technical indicators.

The predictive power of this model comes from:

1. Calculating and continuously updating the coefficients of the indicators in real-time and accurately scaling the coefficients when the time horizon changes.
2. The creativity of creating good indicators. 

Here’s some example of technicals indicators that can be used:

1. The difference between the current price and its exponential moving average (EMA).
2. The difference between two EMAs with different ranges.
3. The difference between three EMAs with 3 different ranges.
4. The difference between bought and sold volume representing order imbalance.
5. The difference between order imbalance and its EMA.