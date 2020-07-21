# BigWig Files 


- BigWig files are a memory efficent way to store continous vaules over a genome and viewing 'coverage' of regions 

### Using BigWigs to visulise Coverage
- Can split by stand to visulise stranded data e.g. bidirectional transcripts
- Can combine several on a single track using track hubs to compare replicates etc

- Can visulise data as 
  - single tracks - e.g. individual replicates
  - merged bigwigs - e.g. merge replicates 
  - Seperate strands 
  - multiple bigwigs on a single track (can do this using parent track and ucsc track hub) - e.g see both strands on a single track
  
  
### Visulising replicates 
  - as individual tracks
  - as merged replicates 
        - encode sum replicates together to a single track https://www.encodeproject.org/help/file-formats/#bigwig
        - https://sites.google.com/site/anshulkundaje/projects/wiggler
            - "Data from biological replicates are stored in individual bigWig files and can be viewed as separate UCSC tracks; however, this may cease to be necessary after the user has concluded that the replicates are highly reproducible. Thus the consortium also provides one bigWig file for each experiment with the reads in all biological replicates pooled and used this file to define the default track for the experiment."
        - can createe mean of replicates using wiggletools
        - bigwigmerge 
  - as several replicates on one track 
  
### Normalising Tracks
  - Accounting for libary size (aka sequencing depth)
      - Counts per million (CPM)
      - RPKM/FPKM
      - TPM 
      - see deeptools 
   
  - Accounting for library size and composition 
      - Useful when comparing across samples that might have very different composition biases e.g. treatments, tissues, artifacts
      - can normalise to size factors e.g. from DESEQ2 or EdgeR 
      
Useful tools 

  - ucsc 
  - wiggletools
      - bigwig -> wiggletools (mean) -> bedgraph -> bigwigs can avoid generating a bw of very large size 
  - deeptools
