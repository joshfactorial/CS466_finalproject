# Joshua Allen
# CS 466 Final project

## Introduction
I have written and implemented multiple sequence matching program that takes several protein sequences and attempts to match with dynamic programming. The first step in implementing this was to cluster the sequences together by how closely related they were using an algorithm called neighbor-joining made popular by the Clustal program. I found this to be an instructive and interesting challenge, even if the results weren't as impressive as I'd hoped. It performed very well on my small test samples, but had multiple problems when trying to align long, real-world sequences.

## Full report
See the PDF document for the [full report.](https://github.com/joshfactorial/CS466_finalproject/blob/master/Allen_Joshua_Final_Project.pdf)

## Note
I discovered an error in my output of the program this morning (5/5/2018) and spent all day trying to isolate the error. I finally figured out that I had declared dtype = int instead of float in my alignment function. Fixing that produced slightly better results. I uploaded the amended program as a different file. The program as initially uploaded does not produce the results I claim because I must have changed that while trying to tweak things to get it to run better before my final data processing run. Anyway, I understand if it can't be considered since I'm past the 12 hour mark as in the email. If so, that's fine because I think the rest of my report basically stands.
