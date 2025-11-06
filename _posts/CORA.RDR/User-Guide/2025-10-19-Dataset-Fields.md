---
layout: default
title:  Dataset Fields
permalink: /CORA.RDR/User-Guide/dataset-fields
nav_order: 60
parent: User Guide
grand_parent: CORA.RDR
---

# Explanation for each dataset field
While you are in the article [Upload Dataset](https://iciq-dmp.github.io/CORA.RDR/User-Guide/upload-dataset) you may 
have encountered the 
need to understand what to write in each metadata field of your dataset. The goal of this article is to explain the 
relevant aspects
of metadata completion in the Datasets published in CORA.RDR and the explanation and possible values to fill in each 
field. 

As you know, each dataset in CORA.RDR contains many metadata fields that describe the dataset and other aspects related 
to it. It 
is very 
important to fill each field with the correct and right data. There is a template that we will use in order to provide
with specific descriptions called "ICIQ_template". The first section of the template is called "Citation Metadata" and 
contains the most important metadata of a dataset, which is the metadata used to cite the dataset.

Here we will add information about each field in this section and what type of information needs.


### Title *(required)*

The **main title** of the dataset. It should be descriptive and consistent with related publications.
If you’re uploading supplementary material for an article, use a clear title such as: `Replication data for “Catalytic 
activation of CO₂ on Cu surfaces”`
**Tip:** Avoid abbreviations or internal references.

Usually, if you are uploading the files for a supplementary materials of an article, the title of 
the dataset is "Replication data for NAME_OF_THE_ARTICLE".

---

### Author *(required)*

The **creator(s)** of the dataset — individuals or organizations who produced or collected the data.
Each author entry can include:

* **Name** *(required)* — Personal or organizational.
  Format for persons: `Family Name, Given Name`. For example: "Mariné-Tena, Aleix"
* **Affiliation** — The institution or organization to which the author belongs.
* **Identifier Type** *(optional)* — e.g., ORCID, ISNI, VIAF, etc.
* **Identifier** *(optional)* — the unique code (e.g. for ORCID, `0000-0002-1234-5678`).
> [!CAUTION] 
> You must provide *at least* one ORCID for each 
  author. The Dataset will not be accepted for publication without this condition.  


**Example:**

| Name               | Affiliation                                        | Identifier Type | Identifier          |
|--------------------| -------------------------------------------------- | --------------- | ------------------- |
| García, Marta      | Institute of Chemical Research of Catalonia (ICIQ) | ORCID           | 0000-0003-1234-5678 |
| Mariné-Tena, Aleix | Institute of Chemical Research of Catalonia (ICIQ) | ORCID           | 0000-0001-9273-1203 |

**Tips:**

* Use institutional affiliation, not the project name.
* If multiple authors, list all in their order of contribution.

---

### Contact *(required)*

The **person or organization** users can reach with dataset questions.
Each entry includes:

* **Name** *(required)* — Person or organization.
* **Affiliation** — Institutional affiliation.
* **E-mail** *(required)* — Contact address for inquiries.

**Example:**

| Name               | Affiliation | E-mail                                    |
|--------------------|-------------|-------------------------------------------|
| Pérez, Ana         | ICIQ        | [aperez@iciq.es](mailto:aperez@iciq.es)   |
| Mariné-Tena, Aleix | ICIQ        | [amarine@iciq.es](mailto:amarine@iciq.es) |

If the contact is an institutional mailbox, use a functional address (e.g., `data@iciq.es`).

---

### Description *(required)*

A **summary** describing the purpose, content, and scope of the dataset.
Include:

* The context of data collection,
* The methodology used,
* The type of data (e.g., experimental spectra, computational models),
* And any relevant details on usage or limitations.

You can also provide:

* **Date** — When the description was added or updated.

**Example:**

> This dataset contains raw and processed data used to generate the results of the publication “Activation of CO₂ on 
> Cu surfaces”. The dataset includes computational input/output files and experimental spectra.

Supports limited HTML tags for formatting (`<p>`, `<b>`, `<i>`, `<ul>`).

---

### Subject *(required)*

Defines the **broad field(s) of study** related to the dataset.
You can select one or more from the controlled list:

**Available subjects:**

* Agricultural Sciences
* Arts and Humanities
* Astronomy and Astrophysics
* Business and Management
* Chemistry
* Computer and Information Science
* Earth and Environmental Sciences
* Engineering
* Law
* Mathematical Sciences
* Medicine, Health and Life Sciences
* Physics
* Social Sciences
* Other


**Tips:**

In ICIQ datasets probably we will use `Chemistry` or `Physics`

---

### Keyword *(required)*

Specific **terms or phrases** that describe key aspects of the dataset.
Each keyword entry includes:

* **Term** *(required)* — The actual keyword (e.g., “Catalysis”, “CO₂ reduction”).
* **Term URI** *(optional)* — Link to a term definition or ontology (e.g., Wikidata, MeSH...).
* **Controlled Vocabulary Name** *(optional)* — e.g., `MeSH`, `LCSH`, `GEMET`, `CHEBI`, `RXNO`, `Wikidata`...
* **Controlled Vocabulary URL** *(optional)* — Link to the vocabulary site.

We do recommend the usage of RXNO for naming reactions and substances, ChEBI for naming proteins and biologically active
proteins, MeSH for general therms and Wikidata for the rest of concepts. 

**Example:**

| Term             | Term URI                                                                                   | Vocabulary Name | Vocabulary URL                                       |
|------------------|--------------------------------------------------------------------------------------------|-----------------| ---------------------------------------------------- |
| Catalysis        | [https://www.wikidata.org/wiki/Q188928](https://www.wikidata.org/wiki/Q188928)             | Wikidata        | [https://www.wikidata.org](https://www.wikidata.org) |
| Caffeine         | [https://www.ebi.ac.uk/chebi/CHEBI:27732](https://www.ebi.ac.uk/chebi/CHEBI:27732)         | ChEBI           | [https://www.ebi.ac.uk/chebi](https://www.ebi.ac.uk/chebi) |
| Archael Proteins | [https://www.ncbi.nlm.nih.gov/mesh/](https://www.ncbi.nlm.nih.gov/mesh/)                   | MeSH            | [https://www.ebi.ac.uk/chebi](https://www.ebi.ac.uk/chebi) |
| Zinc atom        | [http://purl.obolibrary.org/obo/RXNO_0000000](http://purl.obolibrary.org/obo/RXNO_0000000) | RXNO            | [http://purl.obolibrary.org/obo](http://purl.obolibrary.org/obo) |

**Tip:** Choose 3–10 relevant keywords.

---

### Related Publication

Used to reference any **publication(s)** associated with the dataset — typically journal articles that describe or use 
the data.
Each entry includes:

* **Relation Type** — Defines the relationship between dataset and publication. Options include:

  * *Is Cited By*
  * *Cites*
  * *Is Supplement To*
  * *Is Supplemented By*
  * *Is Referenced By*
  * *References*
* **Citation** — Full bibliographic reference in standard citation format.
* **Identifier Type** — e.g., DOI, arXiv, PMID, ISBN, URL.
* **Identifier** — The specific code (e.g., `10.1038/s41586-024-00000-1`).
* **URL** — Link to the publication (DOI or publisher page).

**Example:**

> Relation Type: *Is Supplement To*
> Citation: *M. García et al., “Activation of CO₂ on Cu surfaces”, Nature Chemistry, 2024.*
> Identifier Type: DOI
> Identifier: `10.1038/s41586-024-00000-1`
> URL: `https://doi.org/10.1038/s41586-024-00000-1`

*Tips:*
The object and subject of the relations can be confusing. To clarify, we can add "my dataset" before the type of 
relation. For example: *My dataset* **is supplement to** *this reference*, *My dataset* **cites** *this reference*

---

### Notes

Free-text field for **additional information** not covered elsewhere.
Use it for:

* Special acknowledgements.
* Internal comments relevant to future reuse.
* Description of some file structure not covered elsewhere

**Example:**

> The data files include an additional folder with intermediate outputs not used in the final publication but relevant 
> for reproducibility.

---

### Language *(required)*

#### What this field means

Select the **language(s) used in the dataset’s files** (data tables, READMEs, code comments, documentation, 
questionnaires, figures’ labels, etc.). It’s **not** the UI language of CORA.RDR.

The widget is a **multi-select** list (checkbox menu). It draws from a large, controlled list of languages 
(ISO-style names). You may pick **one or several**.

#### What to enter

* Choose **every language that appears meaningfully** in the files you are publishing:
  * README / documentation language
  * Column headers / variable labels
  * Free-text survey answers
  * Code comments / notebooks’ narrative text
  * Figure captions / axes labels
* If the dataset mixes languages, **select all** that apply.
* If the files contain **no linguistic content** (pure binaries, numerical arrays, images without text), use the 
  special option **“No linguistic content”**.
* If you truly cannot determine the language, use **“Undetermined”** as a last resort.
* If the dataset intentionally contains **many languages**, you can also use **“Multiple languages”** (`mul`) where
  provided, 

#### Typical selections at ICIQ

* `English`
* `Catalan`
* `Spanish`
  (often combinations of the above)

#### Examples

**Example 1 — Supplementary data with English README + Catalan column headers**

* Language: `English; Catalan`

**Example 2 — DFT outputs (logs in English) + Jupyter notebooks with English narrative**

* Language: `English`

**Example 3 — Spectra (binary/raw) + CSV with symbol-only columns, no words**

* Language: `No linguistic content (zxx)`

**Example 4 — Survey data with free-text answers in Spanish and Catalan**

* Language: `Spanish; Catalan`

**Example 5 — Large multilingual corpus with many languages**

* Language: `Multiple languages (mul)` *(or list the top languages if guidance requires specificity)*

---

### Producer

#### What this field means

**Affiliation** is the **parent or associated organization** of the Producer.
Use it when the Producer is a **person**, a **lab/department**, or any **sub-unit** that belongs to a larger body 
(e.g., an institute, university, consortium).

* If the **Producer is a person** → Affiliation is their institution.
* If the **Producer is an organizational sub-unit** (lab, center, department) → Affiliation is the **umbrella 
  organization**.
* If the **Producer is already the top-level organization** → Affiliation is the same top-level organization.


#### When it becomes required

The Producer block is **conditionally required**: if you enter values in one or more Producer subfields, **Name**
becomes required for that Producer entry. *Affiliation itself remains optional*, but strongly recommended for clarity
when Producer ≠ top-level institution.

#### What to enter

* The **official, canonical name** of the parent organization.
* Avoid acronyms alone if they’re ambiguous; prefer **full name** (you can also add the acronym in **Abbreviated 
  Name**).

#### Formatting guidance

* **Organizations:** `Full Official Name (Acronym)` *(acronym optional)*
* **Departments/Units:** `Parent Organization – Unit Name` *(or just Parent Organization in Affiliation, and Unit in Producer Name)*
* **Persons:** Use the **organization name**; do **not** put personal titles or roles here.

#### Examples

##### Producer is a lab (organizational sub-unit)

* **Name:** `Pérez Group – Heterogeneous Catalysis Lab`
* **Affiliation:** `Institut Català d'Investigació Química (ICIQ)`

##### Producer is a person

* **Name:** `García, Marta`
* **Affiliation:** `Institut Català d'Investigació Química (ICIQ)`

##### Producer is the top-level organization

* **Name:** `Institut Català d'Investigació Química (ICIQ)`
* **Affiliation:** `Institut Català d'Investigació Química (ICIQ)`

##### Multi-layer example (department inside a university or research center)

* **Name:** `Catalyst Selection and Optimization Laboratory (CSOL)`
* **Affiliation:** `Institut Català d'Investigació Química (ICIQ)`

#### Good practices

* **Be specific but concise:** If the Producer Name already contains the lab/unit, put the **umbrella institute** in 
  Affiliation.
* **Use canonical names:** Match the organization’s website and publications.
* **Disambiguate with acronyms:** Add acronym in parentheses to the **Producer’s Abbreviated Name** field, not in 
  Affiliation (unless it’s part of the official style).
* **One entry per Producer:** If you have multiple Producers, each can have **its own Affiliation**.

#### Common pitfalls (and fixes)

* **Using roles/titles** like “PI”, “Professor” → *Affiliation must be an organization name, not a job title.*
* **Only an acronym** (e.g., “ICIQ”) → *Prefer “Institut Català d'Investigació Química (ICIQ)”*

---

### Distributor

**Purpose:** Identify who **distributes/serves copies** of the dataset (often the repository/collection).
**Diff. from Producer:** *Producer* manages/finances creation; *Distributor* publishes/provides access.
**Multiplicity:** You can add **multiple** distributors (primary first). Once any subfield is filled, **Name** is 
expected.

**Fields to fill:**

* **Name** — Official distributor name (person/unit/org). *Required once you add anything here.* Currently, the 
  distributor of ICIQ datasets is the data steward, so you may use `Aleix Mariné-Tena` for this field. 
* **Affiliation** — Parent org. of the distributor. Currently, the 
  distributor of ICIQ datasets is the data steward, so you may use `Institut Català d'Investigació Química (ICIQ)` as 
  the producer affiliation. 
* **Abbreviated Name** — Short form/acronym used in badges. In our case `Aleix Mariné-Tena`.
* **URL** — Public landing page for the distributor. Currently, the 
  distributor of ICIQ datasets is the data steward, so you may use `https://iciq.org/staff/marine-tena-aleix/` for this 
  field.  
* **Logo URL** — **Direct** public link to the logo image (SVG/PNG/JPG).
  *Tip:* Avoid intranet/temporary links; make sure the URL ends with the image file.

**Quick tips:**

* Use **official names** (accents allowed), and a **public, stable** logo URL.
* If Producer **also** distributes, list the org in **both** roles with appropriate URLs.
* Keep entries concise and parallel to the **Producer** block to aid consistency.

**Minimal examples:**

* **Repository as distributor**

  * Name: `CORA.RDR – ICIQ Collection`
  * Abbrev.: `ICIQ`
  * URL: `https://dataverse.csuc.cat/dataverse/ICIQ`
  * Logo URL: `https://…/cora-rdr-iciq.svg`
* **Institute as distributor**

  * Name: `Institut Català d'Investigació Química (ICIQ)`
  * Affiliation: `Centre CERCA`
  * Abbrev.: `ICIQ`
  * URL: `https://iciq.org/`
  * Logo URL: *(public image link, not intranet)*

---

### Deposit Date

**Purpose:** Record the **calendar date the dataset was deposited** in the repository (administrative provenance; distinct from publication or data collection dates).

**Format:** `YYYY-MM-DD` (ISO-8601).
**Example (yours):** `2025-11-03`

**How to fill:**

* Use the **repository’s recorded deposit date** (often auto-filled on submit).
* If entering manually, use the date when the **deposit action completed** (not the project end date, not the article’s publication date).

**Notes & tips:**

* **No time or timezone**—date only.
* This field may differ from **Release/Publication Date** (when the dataset becomes public) and from **Data Collection Dates**.
* When you **update** or **re-deposit** a new version, the deposit date should reflect the **new deposit** for that version.

**Common pitfalls:**

* Using acceptance or publication date → use **deposit** date instead.
* Entering locale formats (e.g., `03/11/2025`) → use **ISO** `2025-11-03`.

---

### Kind of Data

**Purpose:** Specify the **type(s) of data included in the files**. This helps users and indexers understand what they’ll download.
**How to fill:** It’s a **multi-select** list. Choose **all** that apply to your dataset’s contents (not the research domain).

**General tips**

* Be **inclusive but precise**: tick every category that truly appears.
* If your dataset mixes experimental, computational, and documentation, **select multiple**.
* When in doubt, prefer the **most specific** option available.

**Option glossary (what to pick & typical ICIQ examples)**

* **Survey data** – Questionnaires, forms, Likert scales; CSV/TSV with respondent rows.
* **Census/enumeration data** – Population/registry counts, complete listings.
* **Aggregate data** – Summaries/means/totals (e.g., averaged catalytic rates by condition).
* **Clinical data** – Patient/clinical measurements (ensure compliance & de-identification).
* **Event/transaction data** – Time-stamped logs of actions/events (e.g., instrument events).
* **Program source code** – Scripts, packages, notebooks (e.g., Python, R, MATLAB, bash).
* **Machine-readable text** – Structured textual formats for automated parsing (e.g., JSON, XML).
* **Administrative records data** – Institutional records (grants, inventory, instrument usage).
* **Experimental data** – Raw/processed lab outputs: NMR/IR/UV-Vis/MS, XRD, electrochemistry, kinetics, HPLC/GC, etc.
* **Psychological test** – Psychometrics/test batteries (rare for chemistry).
* **Textual data** – Human-readable text corpora, README-heavy datasets, protocols in DOC/PDF/TXT.
* **Coded textual** – Text annotated with codes/tags/categories (e.g., labeled literature corpora).
* **Coded documents** – Documents with structured coding schemes or markup beyond plain text.
* **Time budget diaries** – Time-use logs by participants.
* **Observation data/ratings** – Human ratings/annotations of observations (e.g., microscopy scoring).
* **Process-produced** – Data generated automatically by processes/systems (e.g., ELN exports, LIMS dumps).
* **Other** – Use only if none of the above fits (describe in **Notes**).
* **Compiled data** – Data collected from multiple external sources into one dataset.
* **Encoded data** – Data transformed/encoded for analysis (e.g., one-hot, fingerprints).
* **Genomic data** – Sequencing/omics matrices, FASTQ/FASTA, VCF, etc.
* **Geospatial data** – Coordinates, shapefiles, rasters, trajectories with lat/long.
* **Laboratory notebook** – ELN/PDF scans, exported notebook entries.
* **Measurement and test data** – Calibration runs, instrument qualification, standard tests.
* **Recorded data** – Audio/video recordings, sensor streams not otherwise classified.
* **Simulation data** – Outputs from simulations (e.g., MD trajectories, DFT scans, COMSOL).
* **Images** – Non-medical images: microscopy (SEM/TEM/AFM), plots (PNG/SVG), gel images.
* **Medical images** – DICOM/clinical imaging (MRI/CT/etc.).
* **Video** – MP4/MOV instrument captures, reaction videos, microscopy time-lapse.
* **Sound** – Audio files (WAV/MP3), sonification outputs.
* **Musical composition** – Scores/MIDI, not typical for science.

**Quick mapping for common CORA.RDR chemistry datasets**

* **Spectroscopy/Chromatography:** *Experimental data*, *Measurement and test data*, *(Images) for exported plots*.
* **Crystallography (CIF + refinements):** *Experimental data*, *Images* (diffraction/figures).
* **Electrochemistry/Kinetics:** *Experimental data*, *Measurement and test data*, *Aggregate data* (summary tables).
* **Computational (DFT/MD):** *Simulation data*, *Program source code* (scripts), *Machine-readable text* (JSON/XML), possibly *Images* (figures).
* **ELN exports:** *Laboratory notebook*, *Process-produced*, *Textual data*.
* **Jupyter/analysis repo:** *Program source code*, *Machine-readable text*, *Compiled data* (if multiple sources merged).

**Examples (compact)**

* *NMR (FIDs + processed) + GC–MS + CSV summaries:* **Experimental data; Measurement and test data; Images**
* *DFT outputs (ORCA) + XYZ + notebooks:* **Simulation data; Program source code; Machine-readable text; Images**
* *ELN PDF + raw instrument logs:* **Laboratory notebook; Process-produced; Recorded data**

**Common pitfalls**

* Selecting only *Experimental data* but forgetting **Measurement and test data** for calibrations/QA runs.
* Marking *Images* but not *Experimental data* when images are derived from experiments.
* Using *Other* when a suitable specific category exists—prefer the closest match and explain details in **Description/Notes**.





