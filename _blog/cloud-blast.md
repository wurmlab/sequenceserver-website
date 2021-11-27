---
title: "BLAST in the cloud"
date:   2021-10-25 13:03:32"
categories: blast sequence-search datavisualization
layout: page
author: Yannick
keywords: blast cloud, cloud blast, cloudblast
description: Run BLAST analyses in the cloud to get results faster, or search on unpublished data.
---


# Performing BLAST analyses in the Cloud


![Cloud cluster for faster analysis - Datacenter photo credit Hyacinthe C - https://flic.kr/p/wrJuV7](/img/blog/hpc-cloud-blast.jpg){: width="4403" height="1772" style="max-width:75%; height: auto; padding-left:10%"}

## Why you might want to use the Cloud to run BLAST analyses

There are three main scenarios in which you're likely to want to run BLAST in the cloud.

*Scenario A*: you have **unpublished or proprietary databases** that are not available at the NCBI BLAST website

*Scenario B*: you've been running BLAST on your local computer, but:
* you want results **faster**;
* you have **insufficient memory or storage** space for the BLAST databases and results;
* you want to **avoid clogging up your laptop**'s cpu/processors (note that you should avoid overheating your laptop to [avoid damaging your machine](https://www.lifewire.com/problem-with-overheating-laptops-2377646)).


*Scenario C*: you *could* run blast on your high performance computing cluster (HPC).
* The HPC has plenty of space, RAM, and computing cores, its secure and can host proprietary data.
* But you want to **avoid command-line blast**, because its an effort to run, and difficult to make sense of.
* In this case you may **prefer to use a point-and-click graphical interface** for BLAST and get [BLAST graphics that help you interpret analysis results](/blog/visualizing_blast_results).

*Scenario D*: you're tired of waiting for NCBI BLAST, or want to submit larger queries than what it will support. Sure it's free, but your time is precious and you need to get things done.

## Using cloud computing for BLAST analysis

By using cloud computing for BLAST analysis, you're running BLAST on a server that should have much more computing power than the computer in front of you.

You can run the analyses through a web browser with a point-and-click interface, or in the command-line.

## Mechanisms for running BLAST searches in the Cloud

If you're **happy to use BLAST in the command-line**, you can set things up yourself on one of the major cloud computing platforms (e.g., [OVH](https://www.ovhcloud.com/), Microsoft Azure, or Amazon Web Services), where you pay according to your usage. In particular, NCBI provide [documentation](https://github.com/ncbi/blast_plus_docs) and a BLAST+ Docker image to enable you to set up your own cloud computing environment for running command-line BLAST.

If you want a **simple setup for running BLAST and prefer to use a graphical interface**, you'll probably prefer our [SequenceServer Cloud](/cloud) solution. It makes BLAST analysis accessible through the web browser. Just [point and click to set up BLAST, databases and permissions](/blog/point-and-click-blast-server-configuration). SequenceServer Cloud uses the most recent and powerful versions of BLAST and SequenceServer, which provides many benefits for sensitivity, specificity, [visualization and interpretation](/blog/visualizing_blast_results) (the [paper describing SequenceServer BLAST](/paper) has [been cited by hundreds of researchers](/#users) and is used in labs and companies worldwide).

A SequenceServer Cloud instance for BLAST analysis can be private or publically available:

 * **Private SequenceServer Cloud** instances are highly secured, encrypted and password protected. Access can be only for yourself, or be shared among members of your laboratory, institution or company.  You choose who can have access your instance for performing searches against your sequence databases, and who can access your search results.
 * **Public SequenceServer Cloud** instances are ideal if you want to share your data broadly and allow anyone to search against it. This can be ideal if you sequenced a new genome and want to create an online genome database for your species.

[SequenceServer Cloud](/cloud/) has a low monthly cost, and discounts for students, academics and yearly payments.
