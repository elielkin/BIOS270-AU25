# Write-up 3: 


**Name:** Eliel Akinbami  
**Student ID:** elielkin  
**Date:** 12/11/2025  

---

## Overview  
> This document is a compilation of my submission for writeup3 

---

## Part 1

- 3 tables will be created
- From my understanding, since SLURM is running 5 different jobs, there is the possibility for for one job to try reading df into SQL while another job is doing same. This potentially creates a write-lock error. As such, the try and except phrase is there to have the job run, and not crash in the case of handling a lock error. Instead, it waits for a bit and retries running the job. 

## Part 2
### Time taken pre commenting out index_record_ids()
| # processed IDS | time (secs)|
|------|---------------------|
| 0 | 10        | 
| 10 | 93.7    |
| 20| 165.6 |
| 30|274.7 |
|40| 383.4 |
|50| 480.4 |

### Time taken post commenting out index_record_ids()
| # processed IDS | time (secs)|
|------|---------------------|
| 0 | 7.6       | 
| 10 | 72.8    |
| 20| 137.9 |
| 30|203.5|
|40| 269.1 |
|50| 334.9 |

- The function index_records_ids() makes index for each record_id so that while protein_ids are being looked up, the entire table does not need to be scanned on each run. Instead, the right index can be pulled up. This decreases the run time.

## Part 3
- Chunk size stipulates the maximum number of rows to be parsed on every query. This is necessary when you have a large dataset and you do not want to load it all into memory or you want to avoid processes being killed due to large dataset getting parsed. 


## Part 4
- The data gotten back is one where each row is a protein and each column is the feature for that given protein. So the returned chunk is 1000 proteins with 164 features describing each protein. Different from my field of study but my guess is a for biological use cases, one does not want to compare a single feature across multiple proteins. Rather, the more interesting question is how a set of proteins compare across all given features. It is also easier to create embeddings of each protein if all features are present, thus making clustering and building models much easier. 
- Don't know if there is some biological relevance for 1000 being the chunk size. 