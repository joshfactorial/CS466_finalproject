# Joshua Allen
# CS 466 Final project

## Introduction
I have written and implemented multiple sequence matching program that takes several protein sequences and attempts to match with dynamic programming. The first step in implementing this was to cluster the sequences together by how closely related they were using an algorithm called neighbor-joining made popular by the Clustal program. I found this to be an instructive and interesting challenge, even if the results weren't as impressive as I'd hoped. It performed very well on my small test samples, but had multiple problems when trying to align long, real-world sequences.

## Programming Approach
My approach to writing this program was to investigate the clustal approach with neighbor joining. I used pandas dataframes because of the convenience of indexing with strings, instead of trying to keep track of everything with index numbers. Pandas has a lot of powerful features, even though it is sometimes a pain to implement. I started by implementing a UPGMA algorithm based on this youtube video ([link](https://www.youtube.com/watch?v=c2y9s_E2184&t=340s)), since neighbor-joining is a modification of this apporach. Once that part was working, I modified the equations to introduce the more complex neighbor-joining approach, based on this video [link](https://www.youtube.com/watch?v=AGSuDxQ7gP8). The main problem I ran into was that my alignment approach, based on our inclass discussions of dynamic programming, assigned higher scores to better matches, whereas the approaches outlined in the videos and elsewhere online (mainly: [this document](http://www.srmuniv.ac.in/sites/default/files/files/1(7).pdf)) used a lower score = better match algorithm. Therefore, they sought to minimize the equations and I needed to maximize them to get the correct results. 

The main idea of the clustering algorithm is to compare all the sequences in turn to each other, creating a symmetrical scoring matrix. Once that matrix is in place, you treat every string as a cluster and then base matches on the best scores, then recalulate the new table given the clusters. The UPGMA approach to coming up with the new matches is simply to average the scores in the new clusters to the other clusters and take the maximum. In the neighbor-joining algorithm, you first compute the new scoring table by averaging the scores between the new cluster and the others, same as for UPGMA, but instead of simple finding the minimum distance (or maximum match, as I did), you find the best score for Q(i,j), where

$ Q(i,j) = (r-2)*d(C_i,C_j) - u(C_i) - u(C_j) $

where r is the current number of clusters. Though because I was maximizing, it also made sense to add the u scores onto the 'distance' rather than subtract, and this provided the correct results in my test data. where r is the total number of current clusters. Programmatically, this translates to is setting up a new matrix with the new clusters indexing both rows and columns. It's understood that Q(i,i) = 0 for all i's, so those locations in the matrix are set to zero. The rest are done by computing the distance between the clusters (d(C_i, C_j)), which simply means looking them up in the averaged scoring table, and subtracting the u values, which is the vector formed by summing across the rows of the scoring table. Because the algorithm always groups them two at a time, this approach only relies on the previous version of the scoring table, without pulling in any outside information. The main drawback of this approach, as you'll see below, is that if it is off when you initially score all the matches, those errors will propogate through to the end. Everything depends on the accuracy of your scoring algorithm. I used dynamic programming, which is supposed to be the slow and steady way to find a definite score, but as you'll see, it doesn't always work the way on real data that it does on test data.

For testing this algorithm I used several sequences I found from the above-mentioned PDF which were already scored and clustered. I also tested it using short peptide chains randomly modified with a slightly modified version of the program we wrote for our last homework. Since my test peptide chains started as ten characters and could have at most 2 changes (indels and mutations combined), I'd expect close alignments and indeed this seemed to work just fine.  I also tested the alignmenst against previous class assignments (though with a different scoring matrix than BLOSUM62, since those examples were nucleotides), so I knew those were working as expected, and found they performed perfectly. So I was confident that the algorithm essentially works, but was surprised by what I found when I ran it against real protein chains.

## Data Processing
I examined the monarch butterfly (Danaes plexippus) protein related to circadian clocks as found on [MonarchBase](http://monarchbase.umassmed.edu/). Scientists who study monarch butterflies are very interested in their migration patterns. They seek to answer questions like how do the butterflies know when to migrate, and how do they know where to go, even across multiple generations, as a single migration might span three or four generations. A key component to this migration pattern is the monarchs' circadian rythms. I focused specifically on gene DPOG206046 and the protein it expresses, which acts as the 'clock' for the circadian rhythm. This is the core protein others will modify the expression of to create the circadian rhythm, and ultimately the migration behavior. The MonarchBase lists several analogous proteins in other species, including HMEL008784 in the genus Heliconius, a genus of butterfly in the same family as D. plexippus; BGIBMGA000498-TA in the genus bombyx, a genus of silkmoths in the same order (Lepidoptera) as D. plexippus; Clk-PD in the genus Drosophila (the fruit fly), in the same class as D. pleixppus (insecta); UniRef50_GOYQM3 a protein present in certain pest moths, which are also lepidopterans that are more distantly related, but better studied due to their economic importance. All of these proteins are relatively close to the query protein (55.83%, 50.43%, 55.53%, and 78.75%, respectively, according to MonarchBase). My hope was that my program, though it would likely be slower, would produce some usable results from comparing these five proteins.

When I did my test runs with small proteins, the results of the program were pretty solid. The program runs quickly and produces satisfactory results. For example, on this test data from [this document](http://www.srmuniv.ac.in/sites/default/files/files/1(7).pdf):

![Image](https://github.com/joshfactorial/CS466_finalproject/blob/master/Capture.PNG?raw=true)

Matching these five small subsections produced an adequate output of 

seq1	PEEKSAVTALWGKV--NVDEVGG
seq2	GEEKAAVLALWDKV--NEEEVGG
seq3	PADKTNVKAAWGKVGAHAGEYGA
seq4	AADKTNVKAANSKVGGHAGEYGA
seq5	EHEWQLVLHVWAKVEADVAGHGQ

Though the gaps were a little off of the example, it preserved the major regions highlighted, and produced a clustering that exactly matched the phylogenetic tree in the example. 

The longer matches, however did less well. While the speeds were actually comparable, matching for the entire proteins listed above produced a result with far too many gaps between peptides. These problems led to poor scoring even in the first iteration. My grouping algorithm produced a final cluster of:

(Clk-PD, (BGIBMGA000498-TA, (G0YQM3_SPOEX, (DPOGS206046-PA, HMEL008784-PA))))

Clustal Omega gives a phylogenetic tree of (((BGIBMGA000498-TA, Clk-PD), (HMEL008784-PA,  G0YQM3_SPOEX)), DPOGS206046-PA). This probably reflects this specific protein more than the evolution of the total organism. This volatility of individual proteins is why phylogenetic trees are done with mitochondrial DNA, which is more conserved between species.

An interesting note is when you examine the strict phylogeny of the species as a whole, my grouping makes some sense. It groups the two from the same family, then two from the same order. I'm not sure which of the two moths would be closer related, but the fruit fly would definitely be the least related to the others. They are all in the same class, but totally different orders. It's possible that while my program did poorly on finding related regions in the protein strand, it was able to basically distinguish a rough distance between the species. This could also just be coincidental noise.

See Appendix 1 for the Clustal Omega alignment and Appendix 2 my output alignment. I decided to run my algorithm on a well-aligned output subsection of the Clustal Omega output to see how the matches compare. I compared sections 6 and 7 of the output in Appendix 1

### My output

BGIBMGA000498-TA 	MS----I--ELQ-K-PL-T--C--D---LN-E-S-TK-A-SC--N
HMEL008784-PA 	  YDYYH-FD-DLE-K-VV-T--CH-E-A-LM-Q-K-GELT-SCYYS
Clk-PD 		        YDYY-HF-DDL-D-S--IV-AC-H-E-EL-R-Q-TGE-GKSCYY-
DPOGS206046-PA 	  YDYY-HF-DDL-E-K--VVS-C-H-E-AL-M-Q-KGE-LTSCYY-
G0YQM3_SPOEX 	    YDYY-HF-DDL-E-K--VVT-C-H-E-AL-M-Q-KGE-LTSCYY-


BGIBMGA000498-TA 	--ADIA-KNAKQESA-EPD-NVSEA--D--AS-HGT--I--KDA-PS-EE
HMEL008784-PA 	  -YADID-KSTKQESG-ETD-AVSES--E--QT-RNV--L--KES--S-SE
Clk-PD 		        RF--L-TKG-QQWI-WLQTD-Y--YVS-YHQ-F-N-SKPDYV-VCTHKVV
DPOGS206046-PA 	  RF--L-TKG-QQWI-WLQTR-F--YIT-YHQ-W-N-SKPEFV-VCTHRVV
G0YQM3_SPOEX 	    RF--L-TKG-QQWI-WLQTR-F--YIT-YHQ-W-N-SKPEFV-VCTRRVV


BGIBMGA000498-TA 	N---N-------L-----M--V--------M------------S------
HMEL008784-PA 	  ----D-------A-----M--P--------P------------S------
Clk-PD 		        SYAEV-LKDSRKEG-Q--K-S-GNSNSITNNGSS-KVIASTGTSSKSASA
DPOGS206046-PA 	  SYADII-KSTKQERTETEES-VR---DCDHNGSSL-KD----PSTEDAMV
G0YQM3_SPOEX 	    SYADIA-KSMKQEGAEA-DT-VS---EAEVNRGVM-KE-A--PS-DDAMV


BGIBMGA000498-TA 	--------P-S
HMEL008784-PA 	  ----V---K-S
Clk-PD 		        T-TTLRDFELS
DPOGS206046-PA 	  PV----S-P-S
G0YQM3_SPOEX 	    SM----S-P-S 

### Clustal Omega Output
BGIBMGA000498-TA      ----MSIELQKPLTCD-------------------------------------------L
HMEL008784-PA         YDYYHFDDLEKVVTCHEALMQKGELTSCYYSYA---------------------------
Clk-PD                YDYYHFDDLDSIVACHEELRQTGEGKSCYYRFLTKGQQWIWLQTDYYVSYHQFNSKPDYV
DPOGS206046-PA        YDYYHFDDLEKVVSCHEALMQKGELTSCYYRFLTKGQQWIWLQTRFYITYHQWNSKPEFV
G0YQM3_SPOEX          YDYYHFDDLEKVVTCHEALMQKGELTSCYYRFLTKGQQWIWLQTRFYITYHQWNSKPEFV


BGIBMGA000498-TA      NESTKASCNADIAKNAKQESAEPDN-VSEA-------DASHGTIKDAPSEENNLMVMSPS
HMEL008784-PA         ----------DIDKSTKQESGETDA-VSESEQTRNVL--------KESSSEDAMPPSVKS
Clk-PD                VCTHKVVSYAEVLKDSRKEGQKSGNSNSITNNGSSKVIASTGTSSKSASATTTLRDFELS
DPOGS206046-PA        VCTHRVVSYADIIKSTKQERTETEESVRDCDHNGSSL--------KDPSTEDAMVPVSPS
G0YQM3_SPOEX          VCTRRVVSYADIAKSMKQEGAEAD-TVSEAEVNRGVM--------KEAPSDDAMVSMSPS
 
Again, it suffers from too many gaps. The clusters for this smaller scale match are

((Clk-PD, (DPOGS206046-PA, G0YQM3_SPOEX)), (BGIBMGA000498-TA, HMEL008784-PA))

These results don't improve on the  full sequence results significantly at all, and indicate that further work would need to be done to round out this program.

## Conclusions
All in all, my program would have a long way to go to compete with the Clustal Omega and other multi-align packages available. Options would  be to add more heuristic approaches to sequence matching and introducing an affine gap penalty which would favor grouping the sequences together more. I'd also research more on how proteins specifically are scored to improve the algorithm as it pertains to proteins in particular, since I noticed many of the scoring metrics gave a sense of distance rather than a sense of how good the matches were, in which case you'd seek to minimize distance rather than maximize matchis.

However, I was happy with the clustering part of the program overall, at least as it performed against test strands of few peptides. It took awhile to implement, but for short sequences, where my alignment worked best, the clustering algorithm did too. I feel like this is a promising start, if I wanted to build this up into a larger scale program, because my clustering algorithm was dependent on the scoring algorithm, it's success varied with the alignment as well. So the main focus of further improvement of the program. While it's true many tools already exist that can handle these functions, it was very instructive to try to implement my own version, so I could see what problems the more state-of-the-art versions attempt to solve and what the limitations are of my approach, it gave me the ability to focus what I did compared to what they did. Clustal Omega, for example, is something that has been refined and improved over the years by multiple contributers, so it would have been difficult to compete with that, but by performing my own implementation, I can now examine their code and look at how they improved on the basic ideas.
