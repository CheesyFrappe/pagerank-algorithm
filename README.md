# PageRank Algorithm in Python

## Task:
This algorithhm is one of the projects I've written for [CS50AI](https://cs50.harvard.edu/ai/2020/). You can check my [projects](https://github.com/CheesyFrappe/cs50-ai).<br>
Using a Random Surfer Markov Chain and an Iterative Algorithm, write an AI to rank web pages by importance.


## Background:

Search engines like Google display search results in order of importance using a page-ranking algorithm. The Google PageRank algorithm considers a website as more important (higher page rank), when it is linked to by other imporant websites. Links from less important websites have a lower importance weighting.


## Random Surfer Model:

One way to calculate the PageRanks of a corpus of webpages is to use a random surfer model. This models the behaviour of a web surfer who will start on a random web page and with some probability d (where d is known as the damping factor) randomly click any link on the page, or with with probability 1-d randomly go to any other page in the corpus. This model can be interpreted as a Markov Chain, with each page representing a state, and each page having its own transition model for the probability of moving to any other page next. By sampling a large number states from the Markov Chain, a distribution of the number of visits to each page in the corpus can be obtained, and from it, an estimate of the relative page ranking for each page from 0 to 1 can be calculated.


## Iterative Algorithm:

A page's PageRank can also be calculated using the following recursive mathematical expression:

<p align="center">
  <img src="https://user-images.githubusercontent.com/80858788/194870975-c27326e8-ffcd-49c1-9201-030d20be05ea.png" alt="Quick Look">
</p>

where:
* PR(p) is the PageRank of a given page p
* d is the damping factor
* N is the number of pages in the corpus
* i is each possible page in the corpus
* PR(i) is the PageRank of page i
* NumLinks(i) is the number of links on page i

In order to calculate the PageRank for each page in the corpus, we can start with a basic PageRank for each page of 1 / N, and then iteratively calculate new PageRank values for each page. This continues until PageRank values converge (changes on an iteration are less than a threshold value).


## Usage:
Requires Python(3) to run:

python pagerank.py (corpus_directory)
