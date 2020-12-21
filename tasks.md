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

__Task description.__ The participants are asked to define and implement their ranking approach for a multi-lingual candidate documents list. A good ranking should present users with the most relevant documents regarding a query on top of the result set. Regardless of the language used to pose the query, the retrieval can include candidate documents in multiple languages. Participants can submit type A and type B results. Type A rankings will be based on the most common queries in LIVIVO (see below) while Type B submissions should rank candidate documents for any incoming query. 

__Dataset and lab data.__ [LIVIVO](https://livivo.de) is a search portal developed by [ZB MED - Information Centre for Life Sciences](https://zbmed.de), providing comprehensive access to literature in life sciences, including resources from medicine, health, environment, agriculture, and nutrition. LIVIVO corpus consists of about 80 million documents from more than 50 data sources in multiple languages (e.g., English, German, French) covering a variety of  scholarly publication types (e.g., conferences, preprints, peer-review journals). We provide LiLAS participants with a set of common queries with their corresponding candidate documents (and metadata), which participants will rank according to their relevance regarding the query. We also provide participants with logs regarding which documents have been accessed by users and in which order (e.g., click-through rate, if available). 

__Evaluation.__ Participating approaches will be evaluated in the LIVIVO production system on gains, losses, and ties regarding user preferences (e.g., click-through rate per query and candidates list). We will follow a _Team Draft Interleaving_ (TDI) approach where LIVIVO and participants rankings are interleaved and presented together. This way, we will be able to compare all participating systems against each other.

## Task 2: Research Data Recommendations

* [Task Quick Overview](#summ)
* [Task in Detail](#task)
* [Data](#data)
* [Evaluation Metrics](#eval)


<a id="summ"></a> 
### Task Quick Overview
+ task:
+ input:
+ Submission:


<a id="task"></a> 
### Task in Detail

The main task here is to provide recommendations of research data that are relevant to the publication the user is currently viewing. 
For example, the user is interested in the impact of religion on political elections. She finds a publication regarding that topic, which has a set of research data candidates covering the same topic. The task is to rank the most relevant candidates to the top. Participants can submit type A and type B results. 
Whereas the pre-computed type A results comprise recommendations for existing publications and research data only, the Docker variant in type B will also compute recommendations for new publications and research data.

<a id="data"></a> 
### Data
The data for this tasks is taken from the academic search system [GESIS Search](https://search.gesis.org/) ([Hienert et al. 2019](https://ieeexplore.ieee.org/document/8791137)). Besides social science literature (107k publications), it also provides research data (77k) on social science topics, out of which the participants are given the metadata to all publications and all contained research data.

The publications are mostly in English and German and are annotated with title, abstract, topic. The set of research data candidates for each publication, which is given to the participants as well, is computed based on context similarity between publications and research data.

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

<a id="eval"></a> 

### Evaluation Metrics
With an A/B-testing, the GESIS Search users will be shown the recommendations separated by the users' session-id. This means, for each session-id, STELLA selects one recommendation approach out of all participants. This way, we are able to compare all participating systems against each other without confusing the user with different recommendations for the same publication. 
In both type A and type B, the participating approaches will be evaluated in the GESIS Search productive system, where the _top-k_ (with 3 &le; k &le; 10) recommendations are shown to the user. The evaluation itself is performed using implicit and explicit feedback. For the implicit feedback, we calculate the click-through-rate (CTR) as well as the bounce rate once a user clicks on a recommended dataset. The explicit feedback is gathered via options, such as a _thumbs up_ and _thumbs down_, in which the users can indicate whether the recommendation was relevant to them or not. 
