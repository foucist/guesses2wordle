# Guesses2wordle


## Challenge

> eg, here are the guesses for [data/215.json](data/215.json), can you work out -- with a computer -- what the word must have been?

-- Peter S.

## Context

Wordle is a popular game of guessing the word of the day.  https://www.powerlanguage.co.uk/wordle/

215 is the word of the day for Jan 20th. (215 days since the start of the game on June 18, 2021).  

Each guess must be a valid 5 letter word.  All valid words are included in [data/word-list](data/word-list).

## Thoughts

If you merge all the guesses from [data/215.json](data/215.json) you get something like this:
```
[
  [2, 2, 2, 2, 2],
  [2, 0, 0, 2, 2],
  [2, 2, 0, 0, 2],
  [2, 2, 1, 1, 0],
  [2, 2, 2, 0, 0],
  [2, 2, 0, 1, 0],
  [2, 2, 1, 0, 0],
  [0, 0, 1, 2, 2],
  [2, 2, 0, 0, 0],
  [2, 0, 0, 0, 2],
  [0, 1, 1, 0, 2],
  [0, 1, 0, 0, 2],
  [2, 0, 0, 1, 0],
  [0, 0, 0, 2, 1],
  [0, 2, 0, 1, 0],
  [2, 0, 1, 0, 0],
  [0, 0, 1, 1, 0],
  [0, 0, 1, 0, 0],
  [1, 0, 0, 0, 0],
  [0, 1, 0, 0, 0],
  [0, 0, 0, 0, 0],
]
```

Let's take a word like APPLE.  Does it match all of those guesses?
```
[2, 2, 2, 2, 2] = apple
[2, 0, 0, 2, 2] = a[^p][^p]le #=> abele, addle, agile, aisle, aizle, amble, amole, ancle, anele, angle, anile, ankle, anole, argle, avale, axile, azole
[2, 2, 0, 0, 2] = ap[^p][^l]e #=> apace, apage, apode
```

There's no overlap in words, so it fails.
