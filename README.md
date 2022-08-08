# DamID_Seq_Analysis
Computational protocols to analyse DamiD-deq data


The R markdown shows an example of how differential methylation may be called from 
counts files and then translated into peaks.

The exact analysis does not have to follow the same methods, but other tools could
be used to obtain similar results (for example, DESeq2, Limma...). 
Make sure to observe the same file strucutre for the peak-calling scripts (which 
has no error handling or input checks, sorry).

The peak calling script aggregates neighbouring sites of methylation and opposing 
direction into pairs and keeps aggregating as long as they are signficantly 
differentially methylated. It allows for a single unmethylated tag as long as it 
has the same directionality. 

Finally, the penetration of methylated tags at the core of a peak (1kb around its 
center) is calculated to allow filtering on this metric down the track.
