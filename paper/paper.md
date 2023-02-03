---
title: 'BioHackathon Germany 2022'
title_short: 'BioHackGermany22'
tags:
  - NFDI
  - ISA
  - MIAPPE
  - ARC
authors:
  - name: Daniel Arend
    orcid: 0000-0002-2455-5938
    affiliation: 1
  - name: Sebastian Beier
    orcid: 0000-0002-2177-8781
    affiliation: 2
  - name: Dominik Brilhaus
    orcid: 0000-0001-9021-3197
    affiliation: 6
  - name: Hannah Dörpholz
    orcid: 0000-0002-0476-9699
    affiliation: 2
  - name: Manuel Feser
    orcid: 0000-0001-6546-1818
    affiliation: 1
  - name: Patrick König
    orcid: 0000-0002-8948-6793
    afiliation: 1
  - name: Dennis Psaroudakis
    orcid: 0000-0002-7521-798X
    affiliation: 1
  - name: Cristina Martins Rodrigues
    orcid: 0000-0002-4849-1537
    affiliation: 3
  - name: Andrea Schrader
    orcid: 0000-0002-3879-7057
    affiliation: 4
  - name: Elisa Senger
    orcid: 0000-0001-9984-0971
    affiliation: 2
  - name: Heinrich Lukas Weil
    orcid: 0000-0003-1945-6342
    affiliation: 5

  
affiliations:
  - name: Leibniz Institute for Plant Genetics and Crop Plant Research (IPK) Gatersleben, Germany
    index: 1
  - name: Forschungszentrum Jülich GmbH, Germany
    index: 2
  - name: Albert-Ludwigs-Universität Freiburg, Germany
    index: 3
  - name: Cluster of Excellence on Plant Sciences (CEPLAS) / University of Cologne, Germany
    index: 4
  - name: RPTU Kaiserslautern-Landau, Germany
    index: 5
  - name: Cluster of Excellence on Plant Sciences (CEPLAS) / Heinrich-Heine-University Düsseldorf, Germany
    index: 6
date: 10 January 2023
cito-bibliography: paper.bib
event: BH22DE
biohackathon_name: "BioHackathon Germany 2022"
biohackathon_url:   "https://www.denbi.de/de-nbi-events/1454-biohackathon-germany"
biohackathon_location: "Lutherstadt Wittenberg, Germany, 2022"
group: Project 1/8
# URL to project git repo --- should contain the actual paper.md:
git_url: https://github.com/arendd/biohackgermany22plant
# This is the short authors description that is used at the
# bottom of the generated paper (typically the first two authors):
authors_short: Daniel Arend \emph{et al.} **all authors are in alphabetical order**
---


# Introduction

As part of the BioHackathon Germany 2022, we hereby report on the success of the two projects "MIAPPE Wizard: Enabling easy creation of MIAPPE-compliant ISA metadata for Plant Phenotyping Experiments" and "DataPLANT - Facilitating Research Data Management to combat the reproducibility crisis". Shortly before the actual hackathon, it became apparent to the participants that close coordination between the projects would be very beneficial. Both projects aimed to improve the process of collecting and aggregating metadata on plant experiments, but with different approaches. In the following, we summarize the accomplished work and discuss future developments. 


## "MIAPPE Standard -> Introduction" [Daniel, Sebastian,?]

Back in 2015 [@citesAsAuthority:Krajewski2015], the plant community came together to discuss recommendations on how to best capture plant phenotyping experiments in regards to the data and associated metadata. After another year of discussion and looking at different use cases, the formal "minimal information about plant phenotyping experiment" (short MIAPPE, see also https://miappe.org/) with a reference implementation using ISA-Tab was published [@citesAsAuthority:CwiekKupczyska2016]. ISA-Tab is the file representation of the generic ISA (Investigation - Study - Assay) framework [@citesAsAuthority:RoccaSerra2010], where experiments are hierarchically mapped into the three subgroups. In addition to the ISA-Tab representation, there is now also the ISA JSON representation. Since 2020, the current version v1.1 of MIAPPE was released [@citesAsAuthority:Papoutsoglou2020]. With that its scope was extended to also include woody plants (version 1 primarily covered field crops) and was aligned to other metadata standards (DublinCore, Multi-Crop Passport Descriptors), APIs (BreedingAPI, GnpIS-Ephesis), data models (Crop Ontology) and include controlled vocabulary and ISO norms where possible. In their current form, the MIAPPE specifications cover a set of more than 90 core variables and a further, non-exhaustive list of 40 additional environmental variables and experimental factors.

Although many in the community welcome and frequently cite this metadata standard, the number of MIAPPE-compliant datasets is very limited. Through conversations with biologists and wetlab scientists, criticism is often voiced that there are far too many metadata fields and no one is eager to fill them. The reason often given is the time-consuming manual work that could be used with perceived more important activities, such as analysing the data.
-    Cooperation between projects
-    Swate/ARC Toolkit vs. Web-Based GUI



# MIAPPE Wizard: Enabling easy creation of MIAPPE-compliant ISA metadata for Plant Phenotyping Experiments

Experimental research data is only useful to the research community if it is FAIR. In the plant phenomics domain the MIAPPE standard was developed to provide a minimal checklist for relevant metadata attributes and a suitable data model to describe experiments in a FAIR compliant manner. To publish metadata following these guidelines, frameworks like ISA, describing a machine-readable format to bundle the data, can be used. Nevertheless, the hurdle for the data producer to record and manage their experimental metadata is quite high, because of missing data management experience, a diverse set of tools and rare data stewardship support. To overcome these challenges we decided to implement an intuitive graphical user interface, which guides data producers throught the process of describing their experiments. A step-by-step process supported by smart content recommendations and an appropriate formatting in parallel guarantee a sustainable metadata package without the need to be familiar with ISA/MIAPPE standards.


# DataPLANT - Facilitating Research Data Management to combat the reproducibility crisis

Well maintained research data according to the FAIR principles will benefit everyone. To push towards this goal, the DataPlant consortium proposes the Annotated Research Context (ARC), a FAIR research object built upon existing standards like ISA, CWL and RO-Crate. 

A lot of effort went into writing tools and documentation for creating ARCs. At the BioHackathon Germany 2022, we aimed to further integrate these tools with the biological research community, providing our interfaces through openly available REST APIs. Additionally, making the annotation and storing of experimental data as a researcher as frictionless as possible was another goal. For this, findability and quality of the training materials was being improved.

## NFDI Background [Daniel, Sebastian, Cristina ?, Dominik?]

## ARC Data Container [Lukas, Elisa, Cristina]

# Results

## MIAPPE Wizard Prototype
A first prototype of the MIAPPE Wizard has been developed with the Svelte framework (https://svelte.dev) as a single-page application. In the initial state, the user can decide to start either in questionnaire mode or in form mode. Furthermore, the user can also load a saved ISA-JSON file and continue editing from a previous state. The layout after the start screen consists of three columns, where the left column shows a tree navigation of the current ISA data structure (see Figure 1). The middle column shows forms for data input and the right column shows helpful explanations of the ISA or MIAPPE entities and attributes. The JSON schemas of the ISA data model act as single source of truth to construct the ISA-JSON object structure from the particular ISA entities. Multiple recurring form elements have been implemented generically and are automatically displayed in the appropriate order based on a manually created mapping. The questionnaire mode allows multiple-choice questions as well as step-by-step data entry. The multiple-choice questions can be used to request relevant information about the experiment setup and process in advance of the actual data entry. With the help of this information, certain data fields can be pre-filled or the entire data entry process can be simplified by pre-filling certain form fields for e.g. ontology terms or by hiding complete irrelevant sections.

![Figure 1](https://i.imgur.com/9C5z9F7.png)
*Figure 1: Screenshot of the main layout of the MIAPPE Wizard*

To enrich the user's input with ontology terms, the MIAPPE Wizard can access the DataPlant Ontology Lookup Service via asynchrounous JavaScript requests in the background.
The feature is implemented in a GUI component which allows the user to interactively search a given ontology for terms matching his inputs and then to select and add desired terms from the suggestions (see Figure 2).

![Figure 2](https://i.imgur.com/M1SckDd.png)
*Figure 2: GUI component to interactively look up and add ontology terms to the user's ISA objects.*

Furthermore, we implemented a simple ISA-JSON to ISA-Tab conversion backend based on the python isatools-api which is available at https://webapps.ipk-gatersleben.de/isa-json2tab/json2tab (source code available at https://github.com/IPK-BIT/isa-json2tab). 
The MIAPPE Wizard can submit user generated ISA-JSON to this web service and receives the same information in ISA-Tab representation in response, which it then offers for download through the browser.
This allows the wizard to output metadata in both ISA-JSON and ISA-Tab format.


*(**TODO** "reduced ISA/MIAPPE data model")*[?]

Since ISA-JSON and thus the form generated in the GUI becomes large, the user is easily overwhelmed and can easily lose track. It is therefore essential to provide the user with help to navigate the ISA-JSON object. In MIAPPE Wizard this is realized by a tree view. This is already known to users from many applications and therefore does not require any introduction of the functionality. In the tree view such subobjects are selectable, which have a complex nesting, for example single studies. For lists, such as persons, publications, studies, the content is also displayed, but not clickable, to allow checking for completeness at a glance. The length of the list is displayed next to the node. Clicking a node of the tree view sets the focus of the Wizard to the selected element, hiding everything else. To set the Wizard into its default view, the user can click the Investigation node. To cope with large ISA-JSON objects, the tree view is collapsible.

*(paragraph added by Manuel on 19.01.2023, finished on 31.01.2023)*

* <del>basic GUI components (forms & questionaires)</del> **[Patrick, done]**
* reduced ISA/MIAPPE data model
* <del>tree-navigation implemented</del> **[Manuel, done]**
* <del>REST Connection to DataPlant OLS --> integrated into correspondig GUI components </del> **[Dennis, done(?)]**
* <del>set-up backend service to convert ISAJson to ISATab</del> **[Dennis, done(?)]**
* 

## ArcCommander API

for generating ARCs from MIAPPE Wizard: 
* implement ARCCommander REST API **[Oliver]**
* implement ARC import backend **[Lukas]**

## DataPlant Ontology Service

* provide ontology service consumption interface + documentation **[Kevin]**

In order to expand the ontology service to cover more terms relevant in plant phenotyping experiments, two additional ontologies have been included. The CRediT ontology (Contributer Roles Taxonomy, https://credit.niso.org/), which contains 14 typical contributer roles to further annotate the person information within an investigation, and the MIAPPE ontology, which contains all terms from the MIAPPE data model v1.1 (https://github.com/MIAPPE/MIAPPE/tree/master/MIAPPE_Checklist-Data-Model-v1.1). Challenges we solved during the BioHackathon were correction of the format of the official CRediT .obo file to provide a functioning input file for the ontology service and creation of an .obo file of the MIAPPE ontology that was available only in OWL format. Although ontology format converters could have been used, we preferred to create the OBO file based on the data model to avoid the error prone conversion from OWL to OBO, especially when the OWL file contains datatype properties. Both ontologies could then be included successfully in the ontology service.

In order to provide an interface within the DataPLANT project that facilitates the annotation of plant phenotyping experiments, multiple MIAPPE compliant template files were created using the MS Excel add-in Swate (https://github.com/nfdi4plants/Swate). These template files will help users to document metadata and data in MS Excel format. Users can select from different templates those that fit best their needs and provide them with a list of relevant metadata and data terms that they should include in the description of their experiments in order to make them FAIR. The templates cover different sections of the MIAPPE data model checklist v1.1 and are currently under review to reference the newly added MIAPPE ontology. 
Furthermore, we noticed that the MIAPPE terms could be extended to reach a broader auditorium and cover more use cases. 


* <del>integrate additional plant phenotyping relevant ontologies (CREDIT, PPEO)</del> **[Hannah, Elisa, done]**
* <del>convertion of different ontology formats (obo/owl)</del> **[Hannah, Dennis, done]**
* <del>develop MIAPPE compliant SWATE templates</del> **[Hannah, Elisa: done, just needs to be uploaded to Github?]**


## DataPlant Tool documentation

* improve ArcCommander documentation **[Andrea, ?]**

# Future Tasks

1. Improve ISA representation for MIAPPE -> submit several suggestions to the GIT discussion
2. extend implementation of MIAPPE Wizard:
    *    complete integration of ISA model
    *    complete integration of MIAPPE checklist
    *    add interoperability with other tools like e.g. ArcCommander-Webservice and ISA-JSON-to-ISA-TAB converter
3. test ARC generation with MIAPPE Wizard



# Citation Typing Ontology annotation

You can use CiTO annotations, as explained in [this BioHackathon Europe 2021 write up](https://raw.githubusercontent.com/biohackrxiv/bhxiv-metadata/main/doc/elixir_biohackathon2021/paper.md) and [this CiTO Pilot](https://www.biomedcentral.com/collections/cito).
Using this template, you can cite an article and indicate why you cite that article, for instance DisGeNET-RDF [@citesAsAuthority:Queralt2016].

Possible CiTO typing annotation include:

* citesAsDataSource: when you point the reader to a source of data which may explain a claim
* usesDataFrom: when you reuse somehow (and elaborate on) the data in the cited entity
* usesMethodIn
* citesAsAuthority
* discusses
* extends
* agreesWith
* disagreesWith

## Acknowledgements

...

## References
