---
title: 'BioHackathon Germany 2022'
title_short: 'BioHackGermany22'
tags:
  - ISA
  - MIAPPE
  - ARC
  - NFDI
  - DataPlant
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

Back in 2015 [@citesAsAuthority:Krajewski2015], the plant community came together to discuss recommendations on how to best capture plant phenotyping experiments in regards to the data and associated metadata. After another year of discussion and looking at different use cases, the formal "minimal information about plant phenotyping experiment" (short MIAPPE, see also https://miappe.org/) with a reference implementation using ISA-Tab was published [@citesAsAuthority:CwiekKupczyska2016]. ISA-Tab is the file representation of the generic ISA (Investigation - Study - Assay) framework [@citesAsAuthority:RoccaSerra2010], where experiments are hierarchically mapped into the three subgroups. In addition to the ISA-Tab representation, there is now also the ISA JSON representation. Since 2020, the current version v1.1 of MIAPPE was released [@citesAsAuthority:Papoutsoglou2020]. With that, its scope was extended to also include woody plants (version 1 primarily covered field crops) and was aligned to other metadata standards (DublinCore, Multi-Crop Passport Descriptors), APIs (BreedingAPI, GnpIS-Ephesis), data models (Crop Ontology) and include controlled vocabulary and ISO norms where possible. In their current form, the MIAPPE specifications cover a set of more than 90 core variables and a further, non-exhaustive list of 40 additional environmental variables and experimental factors.

Although many in the community welcome and frequently cite this metadata standard, the number of MIAPPE-compliant datasets is very limited. Through conversations with biologists and wetlab scientists, criticism is often voiced that there are far too many metadata fields and no one is eager to fill them. The reason often given is the time-consuming manual work that could be used with perceived more important activities, such as analysing the data.


# MIAPPE Wizard: Enabling easy creation of MIAPPE-compliant ISA metadata for Plant Phenotyping Experiments

Experimental research data is only useful to the research community if it is FAIR [@citesAsAuthority:Wilkinson2016]. In the plant phenomics domain the MIAPPE standard was developed to provide a minimal checklist for relevant metadata attributes and a suitable data model to describe experiments in a FAIR compliant manner. To publish metadata following these guidelines, frameworks like ISA, describing a machine-readable format to bundle the data, can be used. Nevertheless, the hurdle for the data producer to record and manage their experimental metadata is quite high, because of missing data management experience, a diverse set of tools and rare data stewardship support. To overcome these challenges we decided to implement an intuitive graphical user interface, which guides data producers throught the process of describing their experiments. A step-by-step process supported by smart content recommendations and an appropriate formatting in parallel guarantee a sustainable metadata package without the need to be familiar with ISA/MIAPPE standards.


# DataPLANT - Facilitating Research Data Management to combat the reproducibility crisis

Well maintained research data according to the FAIR principles will benefit everyone. To push towards this goal, the DataPLANT consortium proposes the Annotated Research Context (ARC), a FAIR research object built upon existing standards like ISA, CWL and RO-Crate. 

A lot of effort went into writing tools and documentation for creating ARCs. At the BioHackathon Germany 2022, we aimed to further integrate these tools with the biological research community, providing our interfaces through openly available REST APIs. Additionally, making the annotation and storing of experimental data as a researcher as frictionless as possible was another goal. For this, findability and quality of the training materials was being improved.

## ARC Data Container [Lukas]

The ARC is a FAIR digital object, designed specifically to store, annotate, collaborate and share plant research data. It can be used to thoroughly describe the whole research cycle, starting from growing the plant and ending with the final processed data. For this, it builds on existing standards, namely ISA, CWL, git and RO-Crate. ISA, and by extension also the ARC, is used for a multi-faceted annotation of the experimental workflow, as it is a standard designed to provide human and machine readable structure, that can be filled with any information. This flexibility allows the ARC to be used for a diverse set of experimental workflows, with plant phenotyping being one. Picking the bits of information relevant to annotate the given experiment may be a tricky task, which is being tackled by checklists. 
By creating a MIAPPE ARC, researchers can ensure that all the necessary metadata is captured and organized in a structured way, allowing for easier data discovery and reuse. Furthermore, since the MIAPPE standard is quite extensive, it can serve as a useful example for testing the flexibility and scalability of the ARC data container, as it must be able to accommodate a large number of metadata fields and different types of experimental data. Therefore, at the Hackathon we plan to work towards ways to create MIAPPE compliant ARCs.

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

Since ISA-JSON and thus the form generated in the GUI becomes large, the user is easily overwhelmed and can easily lose track. It is therefore essential to provide the user with help to navigate the ISA-JSON object. In MIAPPE Wizard this is realized by a tree view. This is already known to users from many applications and therefore does not require any introduction of the functionality. In the tree view such subobjects are selectable, which have a complex nesting, for example single studies. For lists, such as persons, publications, studies, the content is also displayed, but not clickable, to allow checking for completeness at a glance. The length of the list is displayed next to the node. Clicking a node of the tree view sets the focus of the Wizard to the selected element, hiding everything else. To set the Wizard into its default view, the user can click the Investigation node. To cope with large ISA-JSON objects, the tree view is collapsible.

Due to the limited time frame we decided to initially adapt a reduced set of the MIAPPE data model for the first prototype of the MIAPPE Wizard, which contains components such as Persons, Publications or Material. We have discussed different solutions for entering the data and implemented data type specific GUI components. After several user tests we will improve the components and add additional implementations to support the full MIAPPE data model. 


## ArcCommander API

As part of our work on the DataPLANT project at the BioHackathon Germany 2022, we have made significant progress on consuming MIAPPE ISA-Json, which is output generated by the MIAPPE Wizard, into ARCs. For this we implemented an ArcCommander REST API and the ISA Json import functionality.

Firstly, regarding the ARC-Commander REST API, we have completed the initial development and have successfully tested the API in a local environment. The API is designed to allow users to interact with the ARC data container using standard RESTful API calls, making it easy to integrate into existing workflows and data management systems. For this, the ArcCommander can be run in a server mode, where the functionality usually accessible by CLI commands can now be called using the REST API.

In addition to the ARC-Commander REST API, we have also made significant progress on the ISA-Json import backend. This component is designed to allow users to import existing experimental metadata into a ARC data container, simplifying the process of migrating data from existing data management systems into the ARC format. We have completed the initial implementation of the backend and have tested it with MIAPPE ISA-Json test data, generated using the official ISA-API. 


## DataPlant Ontology Service

* provide ontology service consumption interface + documentation **[Kevin]**

In order to expand the ontology service to cover more terms relevant in plant phenotyping experiments, two additional ontologies have been included. The CRediT ontology (Contributer Roles Taxonomy, https://credit.niso.org/), which contains 14 typical contributer roles to further annotate the person information within an investigation, and the MIAPPE ontology, which contains all terms from the MIAPPE data model v1.1 (https://github.com/MIAPPE/MIAPPE/tree/master/MIAPPE_Checklist-Data-Model-v1.1). Challenges we solved during the BioHackathon were correction of the format of the official CRediT .obo file to provide a functioning input file for the ontology service and creation of an .obo file of the MIAPPE ontology that was available only in OWL format. Although ontology format converters could have been used, we preferred to create the OBO file based on the data model to avoid the error prone conversion from OWL to OBO, especially when the OWL file contains datatype properties. Both ontologies could then be included successfully in the ontology service.

In order to provide an interface within the DataPLANT project that facilitates the annotation of plant phenotyping experiments, multiple MIAPPE compliant template files were created using the MS Excel add-in Swate (https://github.com/nfdi4plants/Swate). These template files will help users to document metadata and data in MS Excel format. Users can select from different templates those that fit best their needs and provide them with a list of relevant metadata and data terms that they should include in the description of their experiments in order to make them FAIR. The templates cover different sections of the MIAPPE data model checklist v1.1 and are currently under review to reference the newly added MIAPPE ontology. 
Furthermore, we noticed that the MIAPPE terms could be extended to reach a broader auditorium and cover more use cases. 

## DataPlant Tool documentation

During the BioHackathon Germany 2022, we focussed on consolidating scattered ARC Commander documentation comprising a [general description](https://nfdi4plants.org/nfdi4plants.knowledgebase/docs/implementation/ArcCommander.html) of the Arc Commander, wiki, [quickstart](https://nfdi4plants.org/nfdi4plants.knowledgebase/docs/implementation/QuickStart_arcCommander.html) on the user-centred side as well as [developers' documentation](https://nfdi4plants.github.io/arcCommander-docs/) from different GitHub repositories.  

Now, in a one-stop experience, a centralized Arc Commander collection in the [DataPLANT knowledge base](https://nfdi4plants.org/nfdi4plants.knowledgebase/index.html) is available. Users can gather required information to rapidly create their first ARC, to learn in detail about the background of an ARC and to access the Arc Commander developers' documentation.  

Thereby, the user can focus on working in the Annotated Research Context and providing ontology-driven metadata annotation to overcome the reproducibility crisis[@citesAsAuthority:Baker2016] which was centre stage to both projects presented here. In this line, an [expert quickstart](https://nfdi4plants.org/nfdi4plants.knowledgebase/docs/implementation/QuickStart_arcCommander_expert.html) was added proofing to be a significant shortcut even for beginners and only requiring having created at least one ARC previously.  

Carefully balancing speed and user friendliness with structured information, a wiki and additional information were converted into a [manual](https://nfdi4plants.org/nfdi4plants.knowledgebase/docs/implementation/ArcCommanderManual/index.html) for the ARC Commander and embedded into the knowledge base. At the same time, an overhaul of the sidebar was conducted unifying structure, names (e.g. quickstarts) and creating a more simple visual appearance (see Figure 3).  

[![Screenshot of the DataPLANT Knowledge Base (2023-02-17)](https://i.imgur.com/gsCptvb.jpg)](https://nfdi4plants.org/nfdi4plants.knowledgebase/index.html)
*Figure 3: Screenshot of the DataPLANT Knowledge Base landing page with the sidebar and link to the contribution guide and tool-centred centralized reorganization (2023-02-17)* 

For repeatedly occurring questions from the community and hands-on sessions, we initiated a new section which is currently under development, the FAQ section, with questions also provided by attendees.  

From the beginning, the community was invited to contribute to the knowledge base via an "edit this page" option located at the bottom of each page. The respective link leading to the document in the GitHub directory which could be edited there and a pull request can be created. Only upon the first pull request, several user contribution instructions were provided.  

In order to bundle contribution routes and to invite community members at all levels to contribute to the knowlege base, a more detailed, previously prepared [contribution guide](https://nfdi4plants.org/nfdi4plants.knowledgebase/docs/CONTRIBUTING.html) went online during the Hackathon. Multiple links were adjusted, explanations and examples were extended like how to construct an appropriate relative path. Also, a link is provided explaining how to test changes or a new contribution in a local environment prior to a pull request which is requested for this. The contribution guide is currently reached via a link on the knowledgebase landing page.  

The kick-off for the online version of this contribution guide complements the collaborative community approach of the [MIAPPE and DataPLANT projects](#Introduction) at the BioHackathon Germany 2022.  

[Lukas?]

As part of our ongoing effort to improve the user experience with generating ARCs, we have been working on improving our user documentation. Previously, the tool documentation was managed by each developer individually, resulting in a sligthly scattered documentation, with some information being hard to find. We recognize, that clear and comprehensive documentation is crucial for users to be able to make the most of our tools, and we are committed to ensuring that our documentation is up to date, easy to navigate, and accessible to all.

To this end, we have been consolidating our user documentation into a centralized knowledgebase. By bringing all of our documentation together in one place, we aim to make it easier for users to find the information they need. Our knowledgebase includes both general information about our tools and specific how-to guides, and is organized by topic and tool.

In addition to the centralized user documentation, we have also been working on improving the documentation for individual tools. These decentral documentations are targeting power users like devolopers and data stewards, to provide more detailed insights into the workings of the tool, including its architecture, APIs, and codebase. 



# Future Tasks

During the several discussions with those present and the virtual participants, it once again became clear, that ISA representation of the MIAPPE data model still has some shortcommings. We have made some suggestions to address these shortcomming and intend to improve the mapping in the coming months. The developed prototype of the MIAPPE Wizard already showed some comprehensive and useful features. In the next few months, we will try to integrate the complete ISA model as well as the full MIAPPE checklist to enable the Wizard to produce resuable metadata. The MIAPPE Wizard project has already used valuable services of DataPlant, such as the ontology lookup, to improve the functionaliy of the user interface. In future, we want to extend the connection and use more services, e.g. the ARC-Commander for exporting ARC containers besides ZIP files.  

## Acknowledgements

...

## References
