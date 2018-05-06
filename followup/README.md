# Follow-up

I tweaked the program a bit more just to see if I could get my output closer to the Clustal Omega output. Not that anyone but me will care.
I forced the program into a local alignment version of Dynamic programming to see if I got better matches that way. I think it vastly improved the program's output for long sequences, coming much closer to the Clustal Omega output than previously.

As happy as I am with this new alignment, it still is not perfect. I think the main issue comes down to the clustering. It's not clustering the way Clustal Omega does at this scale, so I still need to tweak how my scoring works. Even the first cluster doesn't match what they have. If I can figure that out, I think it will align much closer.

## New clustering:
('BGIBMGA000498-TA', ('Clk-PD', ('HMEL008784-PA', ('DPOGS206046-PA', 'G0YQM3_SPOEX'))))

## New Output:
![link](https://github.com/joshfactorial/CS466_finalproject/blob/master/followup/new%20alignment_Page_1.png?raw=true)
![link](https://github.com/joshfactorial/CS466_finalproject/blob/master/followup/new%20alignment_Page_2.png?raw=true)
![link](https://github.com/joshfactorial/CS466_finalproject/blob/master/followup/new%20alignment_Page_3.png?raw=true)
![link](https://github.com/joshfactorial/CS466_finalproject/blob/master/followup/new%20alignment_Page_4.png?raw=true)
