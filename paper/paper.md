---
title: 'SWAT4HCLS Biohackathon 2026: Template for the very long title'
title_short: 'BioHackEU23 #26: unknown chemical substances'
tags:
  - LLM
  - PubChem
  - unknown chemical substances
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
    orcid: 
    role: Writing – original draft    
  - name: Umit Sude Böhler
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
  - name: 
    ror: 
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
# URL to project git repo --- should contain the actual paper.md:
git_url: https://github.com/AJKellmann/SWAT4HCLS26_hack-5-llm-agents-term-reconciliation/blob/main/paper/paper.md
# This is the short authors description that is used at the
# bottom of the generated paper (typically the first two authors):
authors_short: First Author \emph{et al.}
---


# Introduction


As part of the SWAT4HCLS Hackathon 2026, we report on Project 5.
This project explores the use of Large Language Model (LLM)-based agents for automated reconciliation of domain-specific terminology with structured ontology concepts.
Semantic interoperability remains a major bottleneck in achieving FAIR data integration across biomedical and life sciences domains. Mapping heterogeneous terminology to standardized identifiers from resources such as Wikidata and BioPortal is essential but typically relies on manual curation.This is a time-consuming and difficult to scale process.
Recent advances in LLM-based agent systems provide new opportunities to automate this process by combining semantic similarity, contextual reasoning, and tool-based API interaction. In this project, we evaluate a multi-agent system designed to perform ontology mapping and apply it to real-world biomedical data derived from the Synodos NF2 project.




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
 - Ontlogoy Agent
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








**Data source: Synodos NF2 dataset**

We evaluated the system using a subset of data from the Synodos NF2 Drug Screening Dataset, hosted on Synapse.

Specifically, we used the processed dataset:

- DOI: https://doi.org/10.7303/syn6138237.1
- File: Synodos_DrugScreen_processed_data.tsv

Additional related raw datasets (single-agent and combination screening) were also provided and used as supporting sources of terminology.






## Meeting information
```YAML
biohackathon_name: "SWAT4HCLS Biohackathon 2026"
biohackathon_url: "https://www.swat4ls.org/swat4hcls-biohackathon-2026/"
biohackathon_location: "Amsterdam, The Netherlands"
group: Project 5
git_url: "https://github.com/AJKellmann/SWAT4HCLS26_hack-5-llm-agents-term-reconciliation/blob/main/paper/paper.md"
```

# Formatting

This document use Markdown and you can look at [this tutorial](https://www.markdowntutorial.com/).

## Subsection level 2

Please keep sections to a maximum of only two levels.

## Tables

Tables can be added in the following way, though alternatives are possible:

```markdown
Table: Note that table caption is automatically numbered and should be
given before the table itself.

| Header 1 | Header 2 |
| -------- | -------- |
| item 1 | item 2 |
| item 3 | item 4 |
```

This gives:

Table: Note that table caption is automatically numbered and should be
given before the table itself.

| Header 1 | Header 2 |
| -------- | -------- |
| item 1 | item 2 |
| item 3 | item 4 |

## Figures

A figure is added with:

```markdown
![Caption for BioHackrXiv logo figure](./biohackrxiv.png)
```

This gives:

![Caption for BioHackrXiv logo figure](./biohackrxiv.png)

Figures can be scaled by adding the width or height to the Markdown like this:

```markdown
![Caption for BioHackrXiv logo figure](./biohackrxiv.png){ width=50px }
```

# Other main section on your manuscript level 1

Lists can be added with:

1. Item 1
2. Item 2

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


# Results


# Discussion

...

## Acknowledgements

...

## ReferencesRecent advances in LLM-based agent systems provide new opportunities to automate this process by combining semantic similarity, contextual reasoning, and tool-based API interaction. In this project, we evaluate a multi-agent system designed to perform ontology mapping and apply it to real-world biomedical data derived from the Synodos NF2 project.




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
 - agent 1
 - System 2

**-Ontology Agent**
Selects relevant ontologies using BioPortal recommender services

**-BioPortal Agent**
Retrieves candidate concepts, including labels, synonyms, and definitions

**-Orchestrating Agent**
Integrates results, evaluates candidates, and assigns:
Best matching identifier (Wikidata QID or ontology URI)
SKOS semantic relation (e.g., exactMatch, closeMatch)
Explanation for the mapping





## Meeting information
```YAML
biohackathon_name: "SWAT4HCLS Biohackathon 2026"
biohackathon_url: "https://www.swat4ls.org/swat4hcls-biohackathon-2026/"
biohackathon_location: "Amsterdam, The Netherlands"
group: Project 5
git_url: https://github.com/yourOrganization/your_report_repo
```
The `git_url:` field must have the link to the GitHub repository with your preprint (draft).

## Author information

Information about the authors is given in the [YAML](https://en.wikipedia.org/wiki/YAML) format at the top of this template.
For authors you provide their names, their affiliations. That is the minimum, but as BioHackrXiv is moving to a situation
where more metadata is shared, and used by, for example, EuropePMC, adding additional information ie encouraged.

BioHackathons is about hacking together, and the minimal number of authors for reports is two. This makes a minimal example
look like this:

```yaml
authors:
  - name: First Author
    affiliation: 1
  - name: Last Author
    affiliation: 2
affiliations:
  - name: First Affiliation
    index: 1
  - name: ELIXIR Europe
    index: 2
```

### Author identifiers

Ideally, authors provide their [ORCID](https://orcid.org/) identifier. For affiliations, It is added with the `orcid:` field.
So, and author record would look like this:

```yaml
authors:
  - name: First Author
    affiliation: 1
    orcid: 0000-0000-0000-0000
```

### Research Organization Registry identifiers

Matching the author identifier, the affiliations can be further specified with the
[Research Organization Registry](https://ror.org/) (ROR) identifier.
For example, this is the affiliation identifier can be added with the `ror:` field:

```yaml
affiliations:
  - name: ELIXIR Europe
    ror: 044rwnt51
    index: 2
```

### Contributor Role Taxonomy

A last feature since is minimal support for the Contributor Role Taxonomy (CRediT). You
can specify the role of authors in writing the report with the `role:` field. However,
the authors are responsible for selection the right terms from [CRediT](https://credit.niso.org/).
An example looks like this:

```yaml
authors:
  - name: First Author
    affiliation: 1
    orcid: 0000-0000-0000-0000
    role: Conceptualization, Writing – review & editing
```

### A full examples

A full example then has this structure:

```yaml
authors:
  - name: First Author
    affiliation: 1
    role: Writing – original draft
  - name: Last Author
    orcid: 0000-0000-0000-0000
    affiliation: 2
    role: Conceptualization, Writing – review & editing
affiliations:
  - name: First Affiliation
    index: 1
  - name: ELIXIR Europe
    ror: 044rwnt51
    index: 2
```

# Formatting

This document use Markdown and you can look at [this tutorial](https://www.markdowntutorial.com/).

## Subsection level 2

Please keep sections to a maximum of only two levels.

## Tables

Tables can be added in the following way, though alternatives are possible:

```markdown
Table: Note that table caption is automatically numbered and should be
given before the table itself.

| Header 1 | Header 2 |
| -------- | -------- |
| item 1 | item 2 |
| item 3 | item 4 |
```

This gives:

Table: Note that table caption is automatically numbered and should be
given before the table itself.

| Header 1 | Header 2 |
| -------- | -------- |
| item 1 | item 2 |
| item 3 | item 4 |

## Figures

A figure is added with:

```markdown
![Caption for BioHackrXiv logo figure](./biohackrxiv.png)
```

This gives:

![Caption for BioHackrXiv logo figure](./biohackrxiv.png)

Figures can be scaled by adding the width or height to the Markdown like this:

```markdown
![Caption for BioHackrXiv logo figure](./biohackrxiv.png){ width=50px }
```

# Other main section on your manuscript level 1

Lists can be added with:

1. Item 1
2. Item 2

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


# Results


# Discussion

...

## Acknowledgements

...

## References
