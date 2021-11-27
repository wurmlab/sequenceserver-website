---
title: "Visualizing and interepreting BLAST alignments"
date:   2021-10-17 13:03:32"
categories: blast sequence-search datavisualization
layout: page
author: Yannick
description: SequenceServer incorporates four powerful visualizations that help researchers interpret BLAST alignment results.
redirect-from: visualizing_blast_results
---

# Visualizing and interpreting BLAST alignments

When running BLAST in the command-line, you end up with a large amount of text. If you have one query with one HSP in a single hit sequence of your BLAST database, interpretation is easy.

However, things are more complicated if:

* you have many queries,
* you have multiple HSPs per hit,
* you have multiple hits,
* you have a combination of the above.

It's particularly confusing when multiple aligning segments (HSPs) aren't in chromosomal order. But why should they be? Aligning segments are ordered by biological similarity (e-value). This is great for some contexts, but not necessarily, say when you are trying to understand how many times your query gene is present in the target genome.

**It quickly becomes a mess** trying to integrate large amounts of text and numbers by keeping track of coordinates on the hit sequences, coordinates on the query sequence, and reading frames and DNA strands...

Speaking from experience, the easiest can be to draw a summary picture on a piece of paper. But it's 2021 - computers should be able to automate that!

## A picture is worth 1000 words

Visualizations to make BLAST result interpretation easier exist thanks to many efforts, including those at NCBI, those we made for [GeneValidator](https://doi.org/10.1093/bioinformatics/btw015), the work of Nikos Darzentas with Circoletto and the work of Jeff Wintersinger & James Wasmuth with Kablammo.

We took inspiration from those efforts so that SequenceServer could better help biologists interpret BLAST results.

<div class="container">
  <div class="row justify-content-center">
 	<div class="alert alert-info" style="max-width:75%">
   <p><strong>SequenceServer 2.0 provides all of the visualizations below are in every BLAST result</strong>. Furthermore you can download them in vectorial (SVG) or PNG format, and use them directly for publications. No need to export BLAST results into a different software or to sketch by hand.</p>
  </div>
  </div>
</div>

## SequenceServer's overview of how hit sequences align to the BLAST search query

Everyone who has used NCBI's BLAST will have seen the overview of how hits align to the query sequence. SequenceServer provides a similar overview. A key difference is that in our visualization, darker segments means stronger e-value. This can be more intuitive to understand thatn the somewhat psychedelic colors that NCBI uses by default.

![How hit sequences align to the BLAST query](/img/visualization/BLAST-hits-align-to-different-regions-of-query-sequence.png){: width="4235" height="750" style="max-width:75%; height: auto; padding-left:10%"}
<br/><br/>

## Pairwise alignments of BLAST query and hit sequences showing each HSP

For each hit sequence (horizontal at the bottom), we show how each aligning segment (HSP or High Scoring Pair) aligns to the query sequence (horizontal at the top). Darker alignment means stronger similarity. This visualization is derived from James Wasmuth's work with Kablammo.

![Pairwise overview of HSPs aligning between BLAST query and hit sequence - as generated using SequenceServer's Kablammo integration](/img/visualization/pairwise-overview-of-HSPs-aligning-between-BLAST-query-and-hit-sequence.png){: width="862" height="167" style="max-width:75%; height: auto; padding-left:10%"}

## Comparing the lengths of BLAST queries and the lengths of hits

For each query sequence, we show a histogram of lengths of aligning sequences. Here, the query sequence is more than 1200 amino-acids long, while most hit sequences from the database are much shorter. Most of the hit sequences are 450 to 650 amino-acids long. The hit sequences with the highest BLAST similarity to the query sequence have the darkest color; their lengths cluster around 550-650 amino-acids long.

![Distribution of lengths of hit sequences compared to the query sequence](/img/visualization/blast-hit-protein-length-distribution.png){: width="4235" height="750" style="max-width:75%; height: auto; padding-left:10%"}

## Circos/Circoletto-like overview of segments (HSPs) aligning between BLAST query and hit sequences

Here, three query sequences (in gray) show high similarity to a much larger number of query sequences.

![Circos overview showing BLAST hit alignments](/img/visualization/circos-plot-of-blast-hits-sequenceserver.gif){: width="1079" height="875" style="max-width:75%; height: auto; padding-left:10%"}


## Installing SequenceServer

You can readily perform BLAST analyses using SequenceServer, or use SequenceServer to visualise BLAST XML output. Install it yourself, or use our cloud service to perform and interpret BLAST analyses.


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
