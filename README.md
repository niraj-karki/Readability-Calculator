# Readability-Calculator

## Background
Authors and editors are often concerned with the “readability” of their articles and
manuscripts: how difficult is a sentence to understand? is this document written at a level
appropriate for its target audience? As a student author, you might wish to determine the
cognitive complexity of your term paper or thesis. This leads to the question: are there
any metrics for measuring the concept of readability?

One way to approach this problem is by computing the Flesch Index (FI), a numerical
measure of the readability of English text. Originally invented for evaluating the
difficulty of reading U.S. Army training manuals, it has since become ubiquitous.

## Specifications
Acquire sample documents, analyze them using the Flesch Index, visually communicate
your results, and discuss/interpret any experiments performed.

1. Pre-processing: (Read in and Process the Data): The files consist of text documents downloaded from Project Gutenberg, a free repository of digital documents. As you parse each file you will need to properly handle punctuation, non-alphabetic characters and whitespace. Be sure to document all design decisions. For example, the Flesch Index depends on knowing the number of sentences in a document – how do you define a “sentence” and how does your program determine that number?

2. Analysis: (Compute the Flesch Index (FI) of the data): The first step in the computation is to break the document down into syllables, words and sentences. There are two basic ideas:

* multisyllabic words are more complex than simple words
* sentences with a large number of words (requiring a higher cognitive load to keep everything in memory) are more complex than shorter sentences.

  These two intuitions are captured in the succinct equation below:
  Flesch_Index = 206.835 − 84.6 (𝑛𝑢𝑚𝑆𝑦𝑙𝑙𝑎𝑏𝑙𝑒𝑠/𝑛𝑢𝑚𝑊𝑜𝑟𝑑𝑠 ) − 1.015 (𝑛𝑢𝑚𝑊𝑜𝑟𝑑𝑠/𝑛𝑢𝑚𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑒𝑠)
  where numSyllables is the total number of syllables in the document, numWords is the
  total number of words and numSentences is the total number of sentences.

  A high Flesch Index (~100) indicates text that is easy to read. In the equation above, notice
  that a higher ratio of syllables to words generates a larger term to be subtracted from the
  base, resulting in a lower index, thus indicating a document that is more difficult to read.
  Here are some simple rules to help compute the required numeric values. There are
  numerous variations that you can experiment with, but be sure to apply your rules
  consistently.

3. Visualization: (Display the Results): Put some thought into visually understanding your data. For example, create a histogram
  showing the distribution of polysyllabic words in a document (i.e. what percentage of
  words contain k syllables?). Use a chart to show how different documents (or different
  metrics) compare. Be creative as you explore the data and your results.

    Try to do your visualizations from within your program, using an available graphics
    library (e.g. matplotlib, seaborn, ggplot). The idea is to improve your skills at visually
    exploring and communicating.
