---
layout: post
title:  "Hidden Markov Models"
date:   2019-05-31
banner_image : hmm_banner.png
tags: [R, Python, Data Science, Time Series, Sequential Models, Natural Language Processing, Machine Learning]
---

# Hidden Markov Models

## Good introductions for Hidden Markov Model (HMM)

### On YouTube

  - A friendly introduction to Bayes Theorem and Hidden Markov Models

      - [![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/kqSzLo9fenk/0.jpg)](http://www.youtube.com/watch?v=kqSzLo9fenk)

  - For Math Geeks

      - [![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/TPRoLreU9lA/0.jpg)](http://www.youtube.com/watch?v=TPRoLreU9lA)

### On Medium
  - [Hidden Markov Models Simplified](https://medium.com/@postsanjay/hidden-markov-models-simplified-c3f58728caab)
  - [Hidden Markov Model](https://medium.com/@kangeugine/hidden-markov-model-7681c22f5b9) (with python code)

## Python Libraries
  - [hmmlearn](https://hmmlearn.readthedocs.io/en/latest/tutorial.html)
    - It works good for Gaussian HMM and pre-trained Multinomial HMM.
  - [pomegranate](https://pomegranate.readthedocs.io/en/latest/)
    - The complete python package for HMMs. It has good documentation.
  - [simple-hohmm](https://simple-hohmm.readthedocs.io/en/latest/)
    - It is quite simple to use and works good for Multinomial HMM problems.

## Examples

### Pre-Trained Multinomial HMM using hmmlearn library

```Python

from __future__ import division
import numpy as np
from hmmlearn import hmm

states = ["Rainy", "Sunny"]
n_states = len(states)

observations = ["walk", "shop", "clean"]
n_observations = len(observations)

start_probability = np.array([0.6, 0.4])

transition_probability = np.array([
  [0.7, 0.3],
  [0.4, 0.6]
])

emission_probability = np.array([
  [0.1, 0.4, 0.5],
  [0.6, 0.3, 0.1]
])

model = hmm.MultinomialHMM(n_components=n_states)
model.startprob=start_probability
model.transmat=transition_probability
model.emissionprob=emission_probability

# predict a sequence of hidden states based on visible states
bob_says = np.array([[0, 2, 1, 1, 2, 0]]).T

model = model.fit(bob_says)
logprob, alice_hears = model.decode(bob_says, algorithm="viterbi")
print("Bob says:", ", ".join(map(lambda x: observations[x], bob_says)))
print("Alice hears:", ", ".join(map(lambda x: states[x], alice_hears)))

```
