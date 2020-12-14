---
feature_text: |
  ## Living Labs for Academic Search (LiLAS)
  ### Evaluation Lab at CLEF 2021, 21-24 September 2021
feature_image: "/assets/bucharest.jpg"
layout: page
title: LiLAS @ CLEF2021
---

The *Living Labs for Academic Search* (LiLAS) lab aims to strengthen the concept of user-centric living labs for the domain of academic search by allowing participants to evaluate their retrieval approaches in two real-world academic search systems from the life sciences and the social sciences.
To this end, we provide participants with metadata on the systems' content as well as candidate lists with the task to rank the most relevant candidate to the top. Using the [STELLA-infrastructure](http://www.stella-project.org), we allow participants to easily integrate their approaches into the real-world systems and provide the possibility to compare different approaches at the same time. 

After LiLAS ran as a [workshop lab at CLEF 2020](/2020), in 2021 a full evaluation lab will take place.


## Call for Participation

### How to take part in LiLAS 2021

LiLAS offers two different evaluation tasks: *Academic ad-hoc retrieval* for the multi-lingual and multi-source Life Science search portal LIVIVO and *research data recommendation* within the Social Science portal GESIS Search.

For both tasks, participants are invited to submit

- __Type A : pre-computed runs__ based on previously compiled queries (ad-hoc search) or documents (research data recommendations) from server logs or 
- __Type B : Docker containers__ of full running retrieval/recommendation systems that run within our evaluation framework called STELLA. 


For type A, participants pre-compute result files following TREC run file syntax and submit them for integration into the live systems. For type B, participants encapsulate their retrieval system into a Docker container following some simple implementation rules inspired by the OSIRRC workshop at SIGIR 2019. 

We release datasets containing queries and metadata of documents and data sets from the two systems mentioned above for training purposes. We offer a list of candidate documents and candidate research data for each query and seed document, respectively, so participants focus on the actual ranking approaches behind the ad-hoc search and recommendation task.

## Data Sets

We publish two data sets to allow participants to train and compile their systems for the two platforms LIVIVO and GESIS Search: https://th-koeln.sciebo.de/s/OBm0NLEwz1RYl9N

The data sets share a common struture:

```.
├── gesis-search
│   ├── candidates
│   ├── datasets
│   ├── documents
├── livivo
│   ├── candidates
│   ├── documents
│   ├── head-queries
```

For both platforms we release the documents/research data sets and a precompiled set of candidate documents. For futher data set documentation, please refer to the documentation included in the repository. 

## Dates

| Phase                | Date                    | Description   |
| -------------------- | ----------------------- | ------------- | 
| Data release         | December 14 '20         | Date sets for LIVIVO and GESIS Search are released   |
| Training phase 1     | Early January '21       | Tutorials are published and participants are start to develop their systems | 
| Round 1              | March 1 - 28 '21        | Participants' submissions are deployed at LIVIVO and GESIS Search and session logs are collected | 
| Feedback 1           | March 29 '21            | Organizers gather feedback data from session logs and combine them to compute CTR, Wins, Losses, etc. | 
| Training phase 2     | March 30 - April 11 '21 | Participants adapt their systems based on the provided and annotated feedback data | 
| Round 2              | April 12 - May 9 '21    | (Updated) systems are deployed and session logs are collected | 
| Feedback 2           | May 10 '21              | Organizers gather feedback data from session logs and combine them to compute CTR, Wins, Losses, etc. | 
| Paper Submission     | May 28 '21              | Submission of Participant Papers [CEUR-WS] | 

For further details, please refer to the [CLEF 2021 schedule](https://clef2021.clef-initiative.eu/index.php?page=Pages/schedule.html)


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

---

Contact: <lilas@stella-project.org>

LiLAS is part of CLEF 2021.

[<img src="/assets/clef2021_logo.png" height="200">](https://clef2021.clef-initiative.eu/)
[<img src="/assets/clef-association-logo.png" height="200">](https://www.clef-initiative.eu/)

