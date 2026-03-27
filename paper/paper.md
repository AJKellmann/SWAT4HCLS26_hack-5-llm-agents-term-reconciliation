---
title: 'SWAT4HCLS Hackathon 2026: Hack 5 llm-agents-term-reconciliation'
title_short: 'SWAT4HCLS Hackathon 2026: llm-agents-term-reconciliation'
tags:
  - LLM
  - Ontology
  - FAIR
  - AI
authors:
  - name: Iurii Savvateev
    orcid: 0009-0000-5159-7239
    affiliation: 1
    role: Software, validation
  - name: Woodward Galbraith
    orcid: 0000-0002-7941-5545
    affiliation: 2
    role: Software, validation
  - name: Linda Hendriks
    orcid: 0009-0000-8403-9401
    role: Writing – original draft, validation    
    affiliation: 3
  - name: Alexander Kellmann
    affiliation: 4
    orcid: 0000-0001-6108-5552
    role: Writing – original draft, validation 
  - name: Nalini Paijens
    affiliation: 5
    orcid: 0009-0007-6481-0407
    role: Writing – original draft    
  - name: Ümit Sude Böler
    orcid: 0009-0009-1820-5200
    affiliation: 6
    role: Writing – original draft, validation   
affiliations:
  - name: Bundesinstitut für Risikobewertung (de), BfR
    ror: 03k3ky186
    index: 1
  - name: Northeastern University
    ror: 04t5xt781
    index: 2
  - name: Leiden University Medical Center
    ror: 05xvt9f17
    index: 3  
  - name: Greifswald University Hospital
    ror: 025vngs54
    index: 4 
  - name: University of Amsterdam
    ror: 04dkp9463
    index: 5
  - name: University Medical Center Groningen
    ror: 03cv38k47
    index: 6
date: 26 March 2026
cito-bibliography: paper.bib
event: SWAT4HCLS
biohackathon_name: "SWAT4HCLS Biohackathon 2026"
biohackathon_url: "https://www.swat4ls.org/swat4hcls-biohackathon-2026/"
biohackathon_location: "Amsterdam, The Netherlands"
group: Project 5
git_url: https://github.com/AJKellmann/SWAT4HCLS26_hack-5-llm-agents-term-reconciliation/blob/main/paper/paper.md
authors_short: Savvateev *et al.*
---


# Introduction
As part of the SWAT4HCLS Hackathon 2026, we report on Project 5, Large Language Model-based Agents for Reconcilitiation of Terms.
This project explores the use of Large Language Model (LLM)-based agents for automated reconciliation of domain-specific terminology with structured ontology concepts.
Semantic interoperability remains a major bottleneck in achieving FAIR data integration across biomedical and life sciences domains. Mapping heterogeneous terminology to standardized identifiers from resources such as Wikidata and BioPortal is essential but typically relies on manual curation. This is a time-consuming and difficult to scale process.
Recent advances in LLM-based agent systems provide new opportunities to automate this process by combining semantic similarity, contextual reasoning, and tool-based API interaction. In this project, we evaluate a multi-agent system designed to perform ontology mapping and apply it to real-world biomedical data derived from the [Synodos NF2 project](https://www.synapse.org/Synapse:syn2343195/wiki/62125).



# Methods

**System architecture**

We implemented a multi-agent pipeline for automated mapping of domain-specific terms to ontology concepts. The system integrates:

- Ontology recommendation and search
- Definition retrieval and enrichment
- LLM-based reasoning for semantic alignment
- Assignment of structured identifiers and SKOS relations

The architecture is implemented using LangChain, LangGraph, and a 
Deep Agent framework.

**Multi-agent design**

The system consists of three coordinated agents:
 - Ontology Agent
 - BioPortal Agent
 - Orchestrating Agent

**Ontology Agent**
The ontology agent selects relevant ontologies using the BioPortal recommender services.

**BioPortal Agent**
The Bioportal agent is resposible for retrieving candidate concepts. This includes labels, synonyms, and definitions.

**Orchestrating Agent**
The Orchestrating agent integrates results, evaluates candidates, and assigns:
- Best matching identifier (Wikidata QID or ontology URI)
- SKOS semantic relation (e.g., exactMatch, closeMatch)
- Explanation for the mapping

<!-- Add pipeline image here:
![Alt text](image_url) -->


**Data source: Synodos NF2 dataset**

We evaluated the system using a subset of data from the Synodos NF2 Drug Screening Dataset, hosted on Synapse.

The dataset can be found accessed trough the DOI down below.

- DOI: https://doi.org/10.7303/syn6138237.1
- File: Synodos_DrugScreen_processed_data.tsv

Additional related raw datasets (single-agent and combination screening) were also provided and used as supporting sources of terminology.





## Case study: NF Data Portal 
In the US funding agencies often require projects to upload experimental data to public data portals. This data sharing however, is often done after publication and thus user-submitted data critically lacks standardization and annotation. As a result while biomedical data portals, often contain large amounts of experimental data findability and usability are large scale bottlenecks limiting the re-use of this data in practice.

One such data portal [The NF Data Portal](https://nf.synapse.org/) developed by [Sage Bionetworks](https://sagebionetworks.org/) is a large scale-repository for Neurofibromatosis-type disease studies. While the current NF Data Portal Web-UI, does provide study level metadata, it crucially does not provide grounded annotations of compounds explored in drug-screening studies. As such cross-study drug analysis on the portal currently requires users to manually inspect individual data files. To alleviate this bottle-neck we have applied our method to annotate multiple drug-screening studies from the NF Data Portal.




<!--
# Citation Typing Ontology annotation

You can use [CiTO](http://purl.org/spar/cito/2018-02-12) annotations, as explained in [this BioHackathon Europe 2021 write up](https://raw.githubusercontent.com/biohackrxiv/bhxiv-metadata/main/doc/elixir_biohackathon2021/paper.md) and [this CiTO Pilot](https://www.biomedcentral.com/collections/cito).
Using this template, you can cite an article and indicate _why_ you cite that article, for instance DisGeNET-RDF [@citesAsAuthority:Queralt2016].

The syntax in Markdown is as follows: a single intention annotation looks like
`[@usesMethodIn:Krewinkel2017]`; two or more intentions are separated
with colons, like `[@extends:discusses:Nielsen2017Scholia]`. When you cite two
different articles, you use this syntax: `[@citesAsDataSource:Ammar2022ETL; @citesAsDataSource:Arend2022BioHackEU22]`.

Possible CiTO typing annotation include:

* citesAsDataSource: when you point the reader to a source of data which may explain a claim
* usesDataFrom: when you reuse somehow (and elaborate on) the data in the cited entity
* usesMethodIn
* citesAsAuthority
* citesAsEvidence
* citesAsPotentialSolution
* citesAsRecommendedReading
* citesAsRelated
* citesAsSourceDocument
* citesForInformation
* confirms
* documents
* providesDataFor
* obtainsSupportFrom
* discusses
* extends
* agreesWith
* disagreesWith
* updates
* citation: generic citation
-->

# Results


# Discussion

...

## Acknowledgements

...

## References




