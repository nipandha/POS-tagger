# POS-tagger
Online learnign POS tagger with support for trigrams

The file with viterbi with extension for unknown words is run as:

ParseTraining.py training_file words_file op_file ref_file(optional)

The one with trigrams is run as 

TrigramParse.py training_file words_file op_file ref_file(optional)

The transition frequency has been replaced by the linear interpolated trigram frequency

P= L1* C(t1,t2,t3)/C(t1,t2) + L2*C(t2,t3)/C(t2) + C(t3)/N

where N is the nuber of states in the HMM

The adjustments for unknown states are:
1. Capitalized words are assigned NNP,NNPS with some probability
2. Cardinal numbers are assigned CD
3. Hyphenated are assigned 6 possible states
4. All states are added for otherwise unknown
5. Abbreviated words are assigned NNP with some probability

Note: This is a Python script and may take upto ten minutes to run for the trigram code, but there are no infinite loops, it just runs slowly. 
While running the file, create a util folder and add an __init__.py file inside(I couldn't upload it) along with the entities.py.

