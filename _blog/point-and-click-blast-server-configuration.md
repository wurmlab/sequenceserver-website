---
title: "Point and click BLAST server configuration"
date:   2021-10-17 13:03:32"
categories: blast sequence-search data-visualization gui point-and-click
layout: page
author: Yannick
description: Configuring user access and databases for a SequenceServer Cloud BLAST server
---

# Configuring user access and databases for a SequenceServer Cloud BLAST server

Many SequenceServer users simply see the graphical interface for performing BLAST analyses.

But how do you format FASTA files from genomes or transcriptomes into BLAST databases? How do you make your server secure so that only certain people can access it? If you're running your own server, most of this happens in the command-line.

But if you're using [SequenceServer Cloud](https://sequenceserver.com/cloud) just use a graphical interface to configure your server. Command-line not needed.

## Database and User administration dashboards for a SequenceServer Cloud BLAST server

Each SequenceServer Cloud BLAST instance has a point-and-click administration dashboard.

This dashboard enables the main user to:
 - add databases (see more below)
 - remove databases
 - rename databases
 - add users by entering their email address
 - remove users

The administration dashboard of each SequenceServer Cloud instance is accessible at `https://myspecies.sequenceserver.com/edit`. It looks like this:

![Screenshot of blast interface dashboard for adding users and databases](/img/blast-setup/add-blast-database-interface.png).

## Adding Users

If your SequenceServer Cloud instance is private, you can grant access to colleagues by entering their emails and clicking "Add user". They will receive an email with a link to the BLAST interface.

![User access granted to BLAST database](/img/blast-setup/user-added-notification.png)

When a user tries to access the BLAST interface, they will be asked to enter their email address, and will receive an email with a login link.

SequenceServer instances can also be publicly accessible. In that case, no user-specific things are required.

_Some organizations need SequenceServer to interface with other login mechanisms, or prefer, for example restricting access to particular IP addresses, or using a generic http password. Because such constraints are organization-specific, they cannot be set through the dashboard - please get in touch and we'll implement._

## Adding BLAST databases

The bottom of the screenshot shows where you can add new data to be used as BLAST databases. Here, you can drag and drop (or select) individual FASTA files or gzipped FASTA files. We automatically detect whether they are protein or nucleotide FASTA files and format them into BLAST databases.

You can also batch upload many FASTA files as a single .zip or .tar.gz.

Finally, you can also upload .zip or .tar.gz archives of preformatted databases.

## BLAST search history

By default, a button at the top of the dashboard allows the administrator to view the search history of all users. This can also be deactivated, or be made accessible to all users.

Having an overview of searches performed can be a handy way for researchers to go back to a previous result, and for administrators to understand which datasets are most important to users.

![History of BLAST searches](/img/blast-setup/history-of-blast-searches.png)

<div class="container">
  <div class="row justify-content-center">
 	<div class="alert alert-info" style="max-width:75%">
	  <p>By leveraging cloud computing, publication-ready graphics, and a powerful administration interface, SequenceServer Cloud makes it easy to perform sequence search results and to interpret them. <a href="https://sequenceserver.com/cloud/">Learn more</a></p>
	  <p  style="text-align:center"><a href="https://sequenceserver.com/cloud/"><img src="/img/logos/SequenceServer_logo.png" alt="Sequence Search with SequenceServer" width="200pt"/></a></p>
    </div>
  </div>
</div>

<!--
## General considerations for design of biological data visualization

Each of the visualizations has helped us in our interpretation of BLAST results. For each visualization, we tried to respect

We
-->