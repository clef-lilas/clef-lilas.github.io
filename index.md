---
feature_text: |
  ## Living Labs for Academic Search (LiLAS)
  ### Evaluation Lab at CLEF 2021, 21-24 September 2021
feature_image: "/assets/bucharest.jpg"
layout: page
title: LiLAS @ CLEF2021
---

a

The *Living Labs for Academic Search* (LiLAS) lab aims to strengthen the concept of user-centric living labs for the domain of academic search by allowing participants to evaluate their retrieval approaches in two real-world academic search systems from the life sciences and the social sciences.
To this end, we provide participants with metadata on the systems' content as well as candidate lists with the task to rank the most relevant candidate to the top. Using the [STELLA-infrastructure](http://www.stella-project.org), we allow participants to easily integrate their approaches into the real-world systems and provide the possibility to compare different approaches at the same time. 

Please [register at CLEF to take part in LiLAS 2021](http://clef2021-labs-registration.dei.unipd.it).

## Tasks for CLEF 2021

LiLAS offers two different evaluation tasks:

1. __[Ad-hoc retrieval of scientific documents](tasks#task-1-ad-hoc-search-ranking)__ for the multi-lingual and multi-source Life Science search portal [LIVIVO](https://www.livivo.de).
2. __[Research dataset recommendation](tasks#task-2-research-data-recommendations)__ within the Social Science portal [GESIS Search](https://www.gesis.org/en): Given a scientific publication find relevant research data sets (out of a list of candidates).

For both tasks, participants are invited to submit

* __Type A : pre-computed runs__ based on previously compiled queries (ad-hoc search) or documents (research data recommendations) from server logs or 
* __Type B : Docker containers__ of full running retrieval/recommendation systems that run within our evaluation framework called STELLA. 

For type A, participants pre-compute result files following TREC run file syntax and submit them for integration into the live systems. For type B, participants encapsulate their retrieval system into a Docker container following some simple implementation rules inspired by the OSIRRC workshop at SIGIR 2019. 

The [details of the two tasks](tasks) are described seperately. 


## Data Sets

We publish two datasets to allow participants to train and compile their systems for the two platforms [LIVIVO](https://www.livivo.de) and [GESIS Search](https://www.gesis.org/en).
We offer a list of candidate documents and candidate research data for each query and seed document, respectively, so participants focus on the actual ranking approaches behind the ad-hoc search and recommendation task: [https://th-koeln.sciebo.de/s/OBm0NLEwz1RYl9N](https://th-koeln.sciebo.de/s/OBm0NLEwz1RYl9N)

The data sets share a common struture:

```.
├── gesis-search
│   ├── candidates
│   ├── datasets
│   ├── documents
├── livivo
│   ├── candidates
│   ├── documents
```

For both platforms we release the documents/research data sets and a precompiled set of candidate documents. For further data set documentation, please refer to the documentation included in the repository. 

## Dates

* __December 14, 2020__, Data release
* __January + February 2021__, Training phase 1 - code tutorial for the living lab component will be released
* __March 1 - 28 2021__, Round 1 
* __March 29 2021__, Feedback 1
* __March 30 - April 11 2021__, Training phase 2
* __April 12 - May 9 2021__, Round 2
* __May 10 2021__, Feedback 2
* __May 28 2021__, Paper Submission

For further details, please refer to the [CLEF 2021 schedule](http://clef2021.clef-initiative.eu/index.php?page=Pages/schedule.html)


<!--
### Paper Submission Guidelines

Submissions must be as PDF, formatted in the style of the Springer Publications format for Lecture Notes in Computer Science (LNCS). For details on the LNCS style, see [Springer’s Author Instructions](https://www.springer.com/gp/computer-science/lncs/conference-proceedings-guidelines). Authors should use Springer’s proceedings templates, either for LaTeX or for Word, and are encouraged to include their ORCIDs in the papers. 

All submissions must be written in English and should be submitted electronically through the [conference submission system](https://www.easychair.org/conferences/?conf=clef2021).
-->

## Organization

We will have a *half-day workshop* that is split up in two parts. 


### LiLAS 2020 Chairs

- [Philipp Schaer](https://ir.web.th-koeln.de/people/philipp-schaer/), TH Köln, Germany
- [Johann Schaible](https://gesis.org/person/johann.schaible), GESIS, Germany
- [Leyla Jael Garcia-Castro](https://www.linkedin.com/in/leyla-jael-garcia-castro-85384a17/), ZB MED, Germany

<!--
### Program Committee 

- Krisztian Balog, University of Stavanger, Norway
- Joeran Beel, Trinity College Dublin, Ireland
- Birger Larsen, Aalborg University, Denmark
- Vivien Petras, Humboldt University, Germany
- Ansgar Scherp, Ulm University, Germany
- Philipp Mayr, GESIS, Germany
- Tommaso di Noia, Politecnico di Bari, Italy

-->

## Follow us 

[Google Groups](https://groups.google.com/forum/#!forum/clef-lilas)  \|  [GitHub](https://github.com/stella-project) \| <lilas@stella-project.org>


LiLAS is part of CLEF 2021.

[<img src="/assets/clef2021_logo.png" height="200">](https://clef2021.clef-initiative.eu/)
[<img src="/assets/clef-association-logo.png" height="200">](https://www.clef-initiative.eu/)

