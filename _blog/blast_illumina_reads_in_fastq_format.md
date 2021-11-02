---
title: "BLASTing Illumina reads in FASTQ format"
date:   2021-11-01 13:03:32"
categories: blast sequence-search datavisualization
layout: page
author: Yannick
description: BLAST is powerful, but not necessarily apprpriate for analysis of FASTQ files
---

# BLASTing Illumina reads in FASTQ format

BLAST uses FASTA format for queries and for database creation. So the BLAST algorithm doesn't directly understand FASTQ format. This is in part because BLAST was created long before the FASTQ format was created, and because FASTQ files are *typically* inappropriate for BLAST analysis.

FASTQ files typically are the result of Illumina or Nanopore sequencing. FASTQ files thus include a lot of redundancy (many reads from the same subset of the genome or transcriptome, or from a particualr amplicon. When this is the case:

* BLAST analysis will be **slow** because the algorithm needs to search through a much larger set of sequences than if redundancy had been removed. Indeed, FASTQs are typically huge files containing tens to hundreds of millions of read sequences.
* If results are found, they are likely to include a lot of redundancy (many similar reads obtaining high scores). This **makes interpretation difficult**.
* Having a particularly large set of redundant sequences to search through also **reduces BLAST's ability to identify sequence similarities**. This is because BLAST's detection power depends on the size of the query and database. Indeed, the e-value of a particular alignment is lower if your database or search are larger. (E-value is grossly equivalent  to "the number of times I'd find this match by chance if the database were made up of random nucleotides").

## Most of the time if you want ot BLAST a FASTQ file, you're probably not using the best approach

It is likely that you want to first reduce redundancy in your dataset. The most biologically relevant way is often to perform whole genome or transcriptome assembly of your raw reads prior to BLASTing them.

If you do want to work with the raw reads, BLAST often isn't the best way to perform analysis.

## But what if I really do need to run BLAST on FASTQ files?

With the aforementioned caveats that it often is inappropriate to BLAST raw reads, gaining biological insight sometimes does depend on it.

The easiest way of converting FASTQ to FASTA format is to use something like the following `seqtk` command:

```
seqtk seq -A input.fq > output.fasta
```

There are many other ways - I recommend using a tried and tested tool rather than creating your own thing by creatively using grep or perl.


<div class="container">
  <div class="row justify-content-center">
  <div class="alert alert-info" style="max-width:75%">
   <p>By leveraging cloud computing and publication-ready graphics, SequenceServer Cloud makes it easy to perform sequence search results and to interpret them. <a href="https://sequenceserver.com/cloud/">Learn more</a></p>
   <p  style="text-align:center"><a href="https://sequenceserver.com/cloud/"><img src="/img/logos/SequenceServer_logo.png" alt="Sequence Search with SequenceServer" width="200pt"/></a></p>
    </div>
  </div>
</div>

<!--
## General considerations for design of biological data visualization

Each of the visualizations has helped us in our interpretation of BLAST results. For each visualization, we tried to respect

We
-->
