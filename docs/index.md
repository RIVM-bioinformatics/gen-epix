<p align="center">
    <img src="https://raw.githubusercontent.com/RIVM-bioinformatics/gen-epix-api/be6ec13a6f9d39be1e2a6dfbe6ba7b48ad2a2551/docs/assets/Gen-epix-logo.svg" alt="gen-epix-api-logo">
</p>
<p align="center">
    <em>Genomic Epidemiology platform for disease X</em>
</p>

---

# Gen-EpiX: Genomic Epidemiology platform for disease X (beta version)

Gen-EpiX is platform for visualizing and analyzing genomic epidemiology data. It has fine-grained access controls for collaboration between multiple organizations.

---

## Repositories

This project is divided among the following repositories:

- **<a href="https://github.com/RIVM-bioinformatics/gen-epix-api" target="_blank">Gen-EpiX-API</a>**: The backend package developed for Gen-EpiX.
- **<a href="https://github.com/RIVM-bioinformatics/gen-epix-ui" target="_blank">Gen-EpiX-UI</a>**: The frontend ui library developed for Gen-EpiX.
- **<a href="https://github.com/RIVM-bioinformatics/gen-epix-ui-tools" target="_blank">Gen-EpiX-UI-tools</a>**: A library of general purpose frontend tools made for Gen-Epix.
- **<a href="https://github.com/RIVM-bioinformatics/gen-epix-ui-demo-client" target="_blank">Gen-EpiX-demo-client</a>**: A frontend demo-client developed for Gen-EpiX.
- **<a href="https://github.com/RIVM-bioinformatics/gen-epix-e2e" target="_blank">Gen-EpiX-e2e</a>**: A library of Playwright components to help develop end-to-end tests.

---

## Key Features

- **Visualisation**: Visualize cases by time, place, person and also by genome through a phylogenetic tree coupled to the cases.
- **Fine-grained access**: Give different organizations different access rights per disease, down to individual variables. Organizations can manage access of their own users by themselves.
- **Search**: Search and filter cases, including on genetic similarity.
- **Signal detection**: Detect, define and share sets of cases, signals and outbreaks.
- **Disease X**: Any disease and corresponding analysis variables can be added.
- **Data**: Adheres to the Medallion data architecture design pattern. The silver layer consists of normalized and standardized patient or subject data compliant with <a href="https://www.ohdsi.org/data-standardization" target="_blank">OMOP Common Data Model</a>, and a dedicated database for genetic sequence data and computation of phylogenetic trees. The gold layer consists of case data ready for analysis in the form of a single row of data per case.
- **Tech**: OpenAPI compliant API, deployable on cloud or on-premise, support for multiple authentication providers. Python/FastAPI backend and default TypeScript/React frontend available from gen-epix-web.

## Deliberately not in scope

- **Disease-specific knowledge**: Every organization has their own variables that are important for analysis, as well as their own bioinformatics to process genetic sequence data. We therefore avoided any disease-specific code both for the generation of these data and for the analysis variables that can be defined. Only the results are stored.
- **Collaboration-specific knowledge**: Every collaboration or country (e.g. for public health surveillance of diseases) has their own specifics in terms of access rights and any relevant geographic regions. We therefore avoided any country-specific code, both for the type of organizations that have access, and for any geographic data.
