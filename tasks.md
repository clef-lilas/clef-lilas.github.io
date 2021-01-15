---
feature_text: |
  ## Living Labs for Academic Search (LiLAS)
  ### Evaluation Lab at CLEF 2021, 21-24 September 2021
feature_image: "/assets/bucharest.jpg"
layout: page
title: Tasks for LiLAS @ CLEF2021
---

## Task 1: Ad-hoc Search Ranking

__Motivation.__ Finding the most relevant publications to a query remains a challenge in scholarly Information Retrieval systems, even more in multi-lingual and cross-domain environments.

* Task: Given a query and a 100-document candidate list, participants will rank  documents from most to least relevant with regards to the query
* Input Data: [LIVIVO - Metadata Dump File](https://th-koeln.sciebo.de/s/OBm0NLEwz1RYl9N?path=%2Flivivo)
* Submission: Pre-computed rankings or docker containers for live integration into [LIVIVO](https://livivo.de)

__Task description.__ The goal of Task 1 is supporting researchers find the most relevant documents regarding a head query. Participants are asked to define and implement their ranking approach for a multi-lingual candidate documents list. A good ranking should present users with the most relevant documents regarding a query on top of the result set. Multiple languages can be used to pose the query (e.g. English, German, French); regardless of the language used on the query, the retrieval can include candidate documents in other languages. 

__Dataset and lab data.__ We provide training and test datasets comprising [head queries and 100-document candidate list](https://th-koeln.sciebo.de/s/OBm0NLEwz1RYl9N?path=%2Flivivo%2Fcandidates) as JSONL files. Participating head queries will be restricted to keywords-based search or keywords-based search plus AND, OR and NOT operators. 

A head query has an identifier ```qid```, a query string ```qstr``` and a frequency ```freq``` (a measure which indicates how often the query was issued) . An example is shown here:
```python
{"qid": 1001, "qstr": "integrierte AND versorgung", "freq": 12}
```

A candidate list will include the query identifier ```qid``` and corresponding string ```qstr```, together with a list of 100 document ids.
```python
"candidates": ["C951899619", "C676171", "848078", "C765841" ... ]
```
Documents from [3 major scholarly article databases](https://th-koeln.sciebo.de/s/OBm0NLEwz1RYl9N?path=%2Flivivo%2Fdocuments) are also provided so participants can create their own indexes. A document will include the documents id together with other fields. An example is shown here:
```python
{
  "DBRECORDID": "AGRISFR2016215853",
  "TITLE": [
    "Dissection ..."
  ],
  "AUTHOR": [
    "Teyssèdre, Simon"
  ],
  "SOURCE": [
    "Dissection ..."
  ],
  "LANGUAGE": [
    "fra"
  ],
  "DATABASE": [
    "AGRIS"
  ]
}
``` 
__Submission.__ There are two possible submission type A (pre-computed rankings) and B (docker containers for live integration). Participants can submit type A and type B results. Type A rankings will be based on the most common queries in LIVIVO (see "Dataset and lab data" section above) while Type B submissions should rank candidate documents for any incoming query. 
For any questions please join our [Google Groups](https://groups.google.com/forum/#!forum/clef-lilas) or send us en email [lilas@stella-project.org](mailto:lilas@stella-project.org)
We will open registration and submission via our STELLA server close to the submission date.

__Evaluation.__ Evaluation will be based on the Team Draft Interleaving (TDI) approach where LIVIVO and participants rankings are interleaved and presented together. This way, we will be able to compare all participating systems against each other.
* Type A (pre-computed): Participating approaches will be evaluated against a set of predefined head queries gathered from the production system LIVIVO on gains, losses, and ties regarding user preferences (e.g., click-through rate per query and candidates list recorded via logs). We will use TDI to combine results from production and participants.
* Type B (docker containers). Participating approaches will be integrated into the LIVIVO production system and evaluated on live queries on gains, losses, and ties regarding user preferences (e.g., click-through rate per query and candidates list). We will use TDI to combine results from production and participants.

__Living Lab.__ Submissions in the form of docker containers will be integrated into [LIVIVO](https://livivo.de), a library-focused search portal for Life Sciences developed by [ZB MED - Information Centre for Life Sciences](https://zbmed.de). LIVIVO provides a comprehensive access to literature in life sciences, including resources from medicine, health, environment, agriculture, and nutrition. LIVIVO corpus consists of about 80 million documents from more than 50 data sources in multiple languages (e.g., English, German, French) covering a variety of  scholarly publication types (e.g., conferences, preprints, peer-review journals). For LiLAS lab we will use a subset of LIVIVO data, more information under the section above "Dataset and lab data".

## Task 2: Research Data Recommendations

__Motivation.__ Research data is of high importance in scientific research, especially when making progress in experimental investigations. 
However, finding useful research data can be difficult and cumbersome, even if using dataset search engines, such as [Google Dataset Search](https://datasetsearch.research.google.com/). Therefore, one possible solution is to recommend such appropriate research data sets that are based on publications of the user's interest.  

__Task description.__ The main task here is to provide recommendations of research data that are relevant to the publication the user is currently viewing. 
For example, the user is interested in the impact of religion on political elections. She finds a publication regarding that topic, which has a set of research data candidates covering the same topic. The task is to rank the most relevant candidates to the top. Participants can submit type A and type B results. 
Whereas the pre-computed type A results comprise recommendations for existing publications and research data only, the Docker variant in type B will also compute recommendations for new publications and research data.

__Dataset and lab data.__ The data for this tasks is taken from the academic search system [GESIS Search](https://search.gesis.org/) ([Hienert et al. 2019](https://ieeexplore.ieee.org/document/8791137)). Besides social science literature (107k publications), it also provides research data (77k) on social science topics, out of which the participants are given the metadata to all publications and all contained research data.  
The publications are mostly in English and German and are annotated with further textual metadata like title, abstract, topic, persons, and others. Metadata on research data comprises (among others) a title, topics, datatype, abstract, collection method and universe, temporal and geographical coverage, primary investigators, as well as contributors in English and/or German. The set of research data candidates for each publication, which is given to the participants as well, is computed based on context similarity between publications and research data. 

Example of publication:

```python
{'id': 'csa201419416',
 'title': 'The Changing Value of the Child -- A Review of the Literature Regarding Social
 Perceptions of Sick and Dying Children',
 'abstract': 'This article reviews the literature pertaining to the changing value of the child 
 in England since the 19th century, highlighting the relative policy neglect of contemporary sick
 and dying children. The review discusses the relationship between the value of the child, social
 constructions of childhood and social policy. The review demonstrates how the value of the child 
 has altered from one of utility...',
 'topic': ['Children',
  'Child Mortality',
  'Values',
  'Dying',
  'Mortality Rates',
  'Literature Reviews',
  'Child Neglect',
  'Childhood',
  'England']}

```

Example of research data:

```python
{'id': DA3433,
 'title': 'Kindheit, Jugend und Erwachsenwerden 1991-1997- Kinderlängsschnitt 1993-1997',
 'abstract': 'Die Hauptthemen der Studie: Kultur der Kinder, biopsychosoziale Entwicklung und 
 Lebenslauf, Familie, Schule, Kirche und Religion als Entwicklungs- und Sozialisationskontexte,
 Belastungen und Probleme,Väter und Mütter in Ost und...',
 'topic': ['Familie und Ehe', 'Kinder'], 
 'title_en': 'Childhood, Adolencence, and Becoming an Adult 1991-1997- Children Longitudinal 1993-1997',
 'abstract_en': 'The primary topics of the study: culture of children, bio-psycho-social development and 
 course of life, family, school, church and religion as development and socialization context, 
 stress and problems, fathers and mothers in east and ...',
 'topic_en': ['Family life and marriage', 'Children']}
```


__Evaluation.__
With an A/B-testing, the GESIS Search users will be shown the recommendations separated by the users' session-id. This means, for each session-id, STELLA selects one recommendation approach out of all participants. This way, we are able to compare all participating systems against each other without confusing the user with different recommendations for the same publication. 
In both type A and type B, the participating approaches will be evaluated in the GESIS Search productive system, where the _top-k_ (with 3 &le; k &le; 10) recommendations are shown to the user. The evaluation itself is performed using implicit and explicit feedback. For the implicit feedback, we calculate the click-through-rate (CTR) as well as the bounce rate once a user clicks on a recommended dataset. The explicit feedback is gathered via options, such as a _thumbs up_ and _thumbs down_, in which the users can indicate whether the recommendation was relevant to them or not. 
