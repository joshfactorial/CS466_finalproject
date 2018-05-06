# Follow-up

I tweaked the program a bit more just to see if I could get my output closer to the Clustal Omega output. Not that anyone but me will care.
I forced the program into a local alignment version of Dynamic programming to see if I got better matches that way. I think it vastly improved the program's output for long sequences, coming much closer to the Clustal Omega output than previously.

## New clustering:
('BGIBMGA000498-TA', ('Clk-PD', ('HMEL008784-PA', ('DPOGS206046-PA', 'G0YQM3_SPOEX'))))

## New Output:
BGIBMGA000498-TA &t;	 0    --------------------------------------------------MSIEL
HMEL008784-PA&t;&t; 		 0    MDEDGDDKDDSK----RRTRNLSEKKRRDQFNMLLNELGSMVSSNNRKMDKSTVL
Clk-PD&t;&t;&t;&t;MDDESDDKDDTKSFLCRKSRNLSEKKRRDQFNSLVNDLSALISTSSRKMDKSTVL
DPOGS206046-PA &t;&t;		 0    MDDDGDDKDDTK----RRTRNLSEKKRRDQFNMLVNELGSMVSTNNRKMDKSTVL
G0YQM3_SPOEX &t;&t;		 0    MDDDGDDKDDTK----RRTRNLSEKKRRDQFNMLVNELSAMVSTNNRKMDKSTVL


BGIBMGA000498-TA 	 QKPLT--CDLNESTKASCNA-DIAKNAKQESAEPDNVSEADASHGTIKDAPSEENNLMVM
HMEL008784-PA 		 KSTISFLKNHNEITVRS-RAHDV-----QEDWKPTFLSNEEFTY-LVLEA--LEGFVMVF
Clk-PD 				 KSTIAFLKNHNEATDRS-KVFEI-----QQDWKPAFLSNDEYTH-LMLES--LDGFMMVF
DPOGS206046-PA 		 KSTISFLKNHNEITVRS-RAHDV-----QEDWKPAFLSNEEFTY-LVLEA--LEGFVMVF
G0YQM3_SPOEX 		 KSTISFLKNHNEITVRS-RAHDV-----QEDWKPAFLSNEEFTY-LVLEA--LEGFVMVF


BGIBMGA000498-TA 	 SPS---------------------------------------------------------
HMEL008784-PA 		 SATG--------------------------------------------------------
Clk-PD 				 SSMGSIFYASESITSQLGYLPQDLYNMTIYDLAYEMDHEALLNIFMNPTPVIEPRQTDIS
DPOGS206046-PA 		 SASGCIYYVSESVTSLLGHTPGDIINKSIFDLAFVDDRPNLYNILQN-GGTLDPTQV-VT
G0YQM3_SPOEX 		 SATGQIYYVSESITSLLGHNPADVVNKSIFDLACEDDRPSLYNLLQNPGSATDPMHA-LG


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 -QNEVQFQCHLQRGTLDFRDDITYELVQFNGHFR--TN------MEQ-N-ENNDLS----
Clk-PD 				 SSNQITFYTHLRRGGMEKVDANAYELVKFVGYFRNDTNTSTGSSSEVSNGSNGQPAVLPR
DPOGS206046-PA 		 TDNPISFRCRLQRGTLDFRDEVTYELVQFDGHFR--KN------LES-N-ENGHHS----
G0YQM3_SPOEX 		 KENEIRFQCHLKRGSLDFRDETTYELIQFNGHFR--TN------MEPLD-SDDMQS----


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 -YQSD-----------------------QD------------S--SLEWKFLFLDHRAPP
Clk-PD 				 IFQQNPNAEVDKKLVFVGTGRVQNPQLIREMSIIDPTSNEFTSKHSMEWKFLFLDHRAPP
DPOGS206046-PA 		 -YQDE----HESRLLFVCTGRLYMPQLVRDVSLVDTIRSEFTSRHSLEWKFLFLDHRAPP
G0YQM3_SPOEX 		 -YDPD----HESRLLFVCTGRLYTPQLIRDVSLVDSSRSEFTSRHSLEWKFLFLDHRAPP


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 IIGYLPFEVLGTSGYDYYHFDDLEKVVTCHEALMQKGELTSCYY----------------
Clk-PD 				 IIGYMPFEVLGTSGYDYYHFDDLDSIVACHEELRQTGEGKSCYYRFLTKGQQWIWLQTDY
DPOGS206046-PA 		 IIGYLPFEVLGTSGYDYYHFDDLEKVVSCHEALMQKGELTSCYYRFLTKGQQWIWLQTRF
G0YQM3_SPOEX 		 IIGYLPFEVLGTSGYDYYHFDDLEKVVTCHEALMQKGELTSCYYRFLTKGQQWIWLQTRF


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 ---------------------SYADIDKSTKQESGET-DAVSESEQTRNVLKE-SSSEDA
Clk-PD 				 YVSYHQFNSKPDYVVCTHKVVSYAEVLKDSRKEGQKS-----------------------
DPOGS206046-PA 		 YITYHQWNSKPEFVVCTHRVVSYADIIKSTKQERTETEESVRDCDHNGSSLKD-PSTEDA
G0YQM3_SPOEX 		 YITYHQWNSKPEFVVCTRRVVSYADIAKSMKQEGAEA-DTVSEAEVNRGVMKEAPS-DDA


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 M---PPSVKSAATSA---------------------------------------------
Clk-PD 				 ------------------------------------------------------------
DPOGS206046-PA 		 MVPVSPSYMSEASDAFA-TSYNSMSKLASV-KSAATSGSTSATVATLGTAITTASATWPP
G0YQM3_SPOEX 		 MVSMSPSYMSEASDAFGNSSYQPLSQV-SVS-----------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 ------------------------------------------------------------
Clk-PD 				 ------------------------------------------------------------
DPOGS206046-PA 		 RSSYLLYTTGSDTTSVSGGSRSSQRNSSQELQRLPEPALVPQHGIGAQYLEPAPYVGAVG
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 ------------------------------------------------------------
Clk-PD 				 ------------------------------------------------------------
DPOGS206046-PA 		 VPAVLPLSLPPIPVIVAQDQAQLQEQLQRTHRELQQMIVRQQEELRQVKEQLLFARLGIL
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 -----------------------------------------------GSTGATVASVGTS
Clk-PD 				 ------------------------------------------------------------
DPOGS206046-PA 		 QPVINVQDPFTNPEQMPNRSSIMYDGNRQLSYPQTSHQQNHNMPPQ--------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 TTAPASWPRTSHVRYAGSDTASVSGESRSSQRNRLSPHTGVPQQLMTHRVPEPSLVPQHG
Clk-PD 				 ------------------------------------------------------------
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 IGAQYLEPAPYVGAVGVPGVLPLSLPPLPVIVSPDQAQLQWPWQEQLQRTHRELQQMIVR
Clk-PD 				 ------------------------------------------------------------
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 QQEELRQVKEQLLLARLGILQPIINVQDPYAHPEEIQQNQRLPAQILYEGGPRPIGYPPH
Clk-PD 				 ------------------------------------------------------------
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 TQAPPGNQNQHHHMPPPLALFHIAAVLCSLWSKLNLWLESFGIVKTALSRPDLI------
Clk-PD 				 ------------------------------------------------------GNSNSI
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 ------------------------------------------------------------
Clk-PD 				 TNNGSSKVIASTGTSSKSASATTTLRDFELSSQNLDSTLLGNSLASLGTETAATSPAVDS
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 ------------------------------------------------------------
Clk-PD 				 SPMWSASAVQPSGSCQINPLKTSRPASSYGNISSTGISPKAKRKCYFYNNRGNDSDSTSM
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 ------------------------------------------------------------
Clk-PD 				 STDSVTSRQSMMTHVSSQSQRQRSHHREHHRENHHNQSHHHMQQQQQHQNQQQQHQQHQQ
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 ------------------------------------------------------------
Clk-PD 				 LQQQLQHTVGTPKMVPLLPIASTQIMAGNACQFPQPAYPLASPQLVAPTFLEPPQYLTAI
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 ------------------------------------------------------------
Clk-PD 				 PMQPVIAPFPVAPVLSPLPVQSQTDMLPDTVVMTPTQSQLQDQLQRKHDELQKLILQQQN
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 ------------------------------------------------------------
Clk-PD 				 ELRIVSEQLLLSRYTYLQPMMSMGFAPGNMTAAAVGNLGASGQRGLNFTGSNAVQPQFNQ
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 ------------------------------------------------------------
Clk-PD 				 YGFALNSEQMLNQQDQQMMMQQQQNLHTQHQHNLQQQHQSHSQLQQHTQQQHQQQQQQQQ
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 ------------------------------------------------------------
Clk-PD 				 QQQQQQQQQQQQQQQQQQQQQQQQQLQLQQQNDILLREDIDDIDAFLNLSPLHSLGSQST
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 ------------------------------------------------------------
Clk-PD 				 INPFNSSSNNNNQSYNGGSNLNNGNQNNNNRSSNPPQNNNEDSLLSCMQMATESSPSINF
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 ------------------------------------------------------------
HMEL008784-PA 		 ------------------------------------------------------------
Clk-PD 				 HMGISDDGSETQSEDNKMMHTSGSNLVQQQQQQQQQQQILQQHQQQSNSFFSSNPFLNSQ
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 --------------------------------------YMSDASDAFTNSYHRTSQLAHG
HMEL008784-PA 		 ------------------------------------------------------------
Clk-PD 				 NQNQNQLPNDLEILPYQMSQEQSQNLFNSPHTAPGSSQ----------------------
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 GVANVNEHPCYGSMMFPQSYKAGSEPALVPQHGIGAQYLEPDPYVSAVSLPGVLPLPLPP
HMEL008784-PA 		 ------------------------------------------------------------
Clk-PD 				 ------------------------------------------------------------
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 LPIIVSPDQAQIQEQLQRKHEELQQMILRQQEELRQVKEQLLLARLGILQPLINVPNPYA
HMEL008784-PA 		 ------------------------------------------------------------
Clk-PD 				 ------------------------------------------------------------
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 NTEETQQMQRLPTQVSYDRPAQRSISGYSQTQPPPHLSALQPHSQLQHQHQHQHPNQHQH
HMEL008784-PA 		 ------------------------------------------------------------
Clk-PD 				 ------------------------------------------------------------
DPOGS206046-PA 		 ------------------------------------------------------------
G0YQM3_SPOEX 		 ------------------------------------------------------------


BGIBMGA000498-TA 	 PRML
HMEL008784-PA 		 ----
Clk-PD 				 ----
DPOGS206046-PA 		 ----
G0YQM3_SPOEX 		 ----
