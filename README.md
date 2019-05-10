# Magic_the_Gathering_land_probability_calculator (Joe Golton)

Run the calculator:

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/FilterJoe/Magic_the_Gathering_land_probability_calculator/master?filepath=Magic_the_Gathering_land_probability_calculator.ipynb)

Wait about a minute for it to load, Select "Cell" then "Run All" and then scroll to the bottom to see the interactive probability calculator.


## Introduction

This land probability calculator for Magic the Gathering was a fun way for me to cement my understanding of probability theory ([DeGroot and Schervish](http://www.amazon.com/Probability-Statistics-4th-Morris-DeGroot/dp/0321500466), chapter 1), practice probability calculation in Python, and at the same have an interesting MtG tool. I did it with iPython Notebook a few years ago, and in 2019 updated it for Jupyter Notebook, along with some minor corrections.

## What this does

The following defaults for deck construction are generally recommended for beginners:

* 60 card deck
* 24 lands in the deck

There is better than an 85% chance of starting with at least 2 lands when drawing your initial 7 card hand, which the tool shows with its default settings. You can use the sliders to change around any of the numbers and see how probability is impacted for each possible number of lands appearing in the initial hand draw.

It can be useful to think of land tappable creatures as lands for the purposes of this calculation. For example, if you have 20 lands and 4 Mystic Elves, that is essentially equivalent to 24 lands (well, not really, because there are many more ways to lose a Mystic Elf than a land . . . but it's still useful to think of your starting hand this way as you're not likely to lose a Mystic Elf on turn 1).

You may want to consider mulligans in your calculation. Move the mulligan slider to "1" and you'll see the probabilities for the subsequent 6 card draw, as well as the chances of getting below or above your desired range of lands to start with.

I assume for this analysis that mulligans automatically occur when below minimum required land or above maximum required land, but not otherwise. Therefore, the probability, p, of having too little land after 1 or 2 draws (2nd draw only if 1st draw outside of target range) is:

p = p1(below) * (p0(below) + p0(above))

where

* p0 represents probability in a 7 card draw (zero mulligans)
* p1 represents probability in a 6 card draw (1 mulligan)
* p0(below) represents probability that the number of cards drawn is below the required minimum

## Why Jupyter

Jupyter (formerly iPython Notebook) is a natural match for anything that combines math, coding, and (interactive) graphical output. I can quickly prototype and annotate my experiments. I can get output that is cleaner, clearer, and more flexible, including LaTex formatted equations and embedded plots. And the ability to rerun a small part of the code without having to start over from the beginning saves time.

## Requirements

* Python 3.7.3
* ipywidgets
* sympy
* IPython.display


