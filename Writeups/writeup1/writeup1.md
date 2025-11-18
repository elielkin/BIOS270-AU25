# Write-up 1: 


**Name:** Eliel Akinbami  
**Student ID:** elielkin  
**Date:** 11/17/2025  

---

## Overview  
> This document is a compilation of my submission for writeup 1, detailing environment setup. 

---

## Screenshots from setup
#### **Image Example**

![Example placeholder image](./snyderlab.png)
```bash
# Example command line code
echo "Hello, Markdown!"
```

## Answers to SLURM questions
1. From my understanding, 1 SLURM job is submitted containing 3 tasks
2. Given a variable called ***SLURM_ARRAY_TASK_COUNT***, each task checks to if the remainder(modulo) of the the given line corresponds to its task ID. If it does, print out the line number and its value
3. There will be 3 output files with the format and information below

    | File_name | Line numbers      | Values   |
    |------|---------------------|------------------------|
    | **warmup_JOBID_0** | **0, 3** |  **12, 8** |
    | **warmup_JOBID_1** | **1, 4**      | **7, 27**   |
    | **warmup_JOBID_2** | **2,5**   | **91, 30**     |
