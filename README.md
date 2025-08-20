<p align="center">
    <img src="./docs/assets/gen-epix_logo_full.svg" alt="gen-epix-logo">
</p>

---

# Gen-EpiX: Genomic Epidemiology platform for disease X<br>[beta version]

Gen-EpiX is a platform for visualizing and analyzing genomic epidemiology data. It can be used for any disease and has very fine-grained access controls to enable collaboration between multiple organizations. It does not include, by design, bioinformatics pipelines or any other data analysis pipelines.

The platform is currently at the beta release stage and as such not yet usable for production. We are currently working to get the platform released, for use in the Netherlands as the official national platform for laboratory-based surveillance of infectious diseases. Feel free to contact us <a href="mailto:ivo.van.walle@rivm.nl">here</a> if you are interested.

---

## Repositories

This project is divided among the following repositories:

- **<a href="https://github.com/RIVM-bioinformatics/gen-epix-api" target="_blank">gen-epix-api</a>**: the backend package developed for Gen-EpiX.
- **<a href="https://github.com/RIVM-bioinformatics/gen-epix-ui" target="_blank">gen-epix-ui</a>**: the frontend ui library developed for Gen-EpiX.
- **<a href="https://github.com/RIVM-bioinformatics/gen-epix-ui-tools" target="_blank">gen-epix-ui-tools</a>**: a library of general purpose frontend tools made for Gen-Epix.
- **<a href="https://github.com/RIVM-bioinformatics/gen-epix-ui-demo-client" target="_blank">gen-epix-ui-demo-client</a>**: a frontend demo-client developed for Gen-EpiX.
- **<a href="https://github.com/RIVM-bioinformatics/gen-epix-e2e" target="_blank">gen-epix-e2e</a>**: a library of Playwright components to help develop end-to-end tests.

---

## Key Features

- **Visualisation.** Visualize cases by time, place, person and also by genome through a phylogenetic tree coupled to the cases.
- **Fine-grained access.** Give different organizations different access rights per disease, down to individual cases and variables. Organizations can manage access of their own users by themselves.
- **Search.** Search and filter cases, including on genetic similarity.
- **Signal detection.** Detect, define and share sets of cases, signals and outbreaks.
- **Disease X.** Any disease and corresponding analysis variables can be added without requiring additional code.
- **Data.** Follows the <a href="https://dataengineering.wiki/Concepts/Data+Architecture/Medallion+Architecture" target="_blank">Medallion data architecture</a> design pattern. The silver layer consists of normalized and standardized patient or subject data compliant with the <a href="https://www.ohdsi.org/data-standardization" target="_blank">OMOP Common Data Model</a> standard, and a dedicated database for genetic sequence data and computation of phylogenetic trees developed with input from public health institutes from several countries. The gold layer consists of case data ready for analysis in the form of a single row of data per case, typically called a line list by epidemiologists. Demo data are included to be able to quickly get started and see the possibilities.
- **Tech.** OpenAPI compliant API, deployable on cloud or on-premise, support for multiple authentication providers. Python/FastAPI backend and default TypeScript/React frontend.

## Deliberately not in scope

- **Disease-specific knowledge.** Every organization has their own variables that are important for analysis, as well as their own bioinformatics pipelines to process genetic sequence data. We therefore avoided any disease-specific code both for the generation of these data and for the analysis variables that can be defined. Only the results are stored.
- **Collaboration-specific knowledge.** Every collaboration or country (e.g. for public health surveillance of diseases) has their own specifics in terms of access rights and any relevant geographic regions. We therefore avoided any country-specific code, both for the type of organizations that have access, and for any geographic data.
- **Source data.** Every organization has their own applications in which their source data are stored. This bronze layer, in Medallion data architecture terms, is fully out of scope. However, the gen-epix-api package, and in particular the domain classes of the silver layer parts (OMOP and sequence databases), can be imported in any Python-based workflows from bronze to silver layer to facilitate development.

## Funding

This work was funded by the European Union under the EU4Health Programme (EU4H), project IDs 101102070 (UNITED4Surveillance) and 101113520 (NLWGSHERA2).

<img src="./docs/assets/cofunded_EU_logo.png" alt="cofunded-EU-logo" width = 400>

*Disclaimer: Funded by the European Union. Views and opinions expressed are however those of the author(s) only and do not necessarily reflect those of the European Union or Health and Digital Executive Agency. Neither the European Union nor the granting authority can be held responsible for them.*
