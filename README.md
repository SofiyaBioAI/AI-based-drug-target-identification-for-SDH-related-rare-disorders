# 🧬 AI-Assisted Drug Target Identification for SDH-Related Rare Disorders

<p align="center">

<img src="https://img.shields.io/badge/Domain-Computational%20Drug%20Discovery-blue?style=for-the-badge">
<img src="https://img.shields.io/badge/Bioinformatics-Structural%20Biology-green?style=for-the-badge">
<img src="https://img.shields.io/badge/Molecular%20Docking-AutoDock%20Vina-orange?style=for-the-badge">
<img src="https://img.shields.io/badge/Chemoinformatics-RDKit-red?style=for-the-badge">
<img src="https://img.shields.io/badge/Python-3.x-yellow?style=for-the-badge&logo=python">
<img src="https://img.shields.io/badge/Status-Research%20Prototype-purple?style=for-the-badge">

</p>

<p align="center">
<b>A computational drug-discovery workflow for prioritizing small molecules against succinate dehydrogenase (SDH)-related protein targets associated with rare disorders.</b>
</p>

---

## 📌 Project Overview

This project develops a **computational drug-discovery pipeline** for the identification and prioritization of small-molecule candidates against selected protein structures associated with **succinate dehydrogenase (SDH)-related rare disorders**.

The workflow integrates:

* 🧬 Protein structure preparation
* 🧪 Ligand dataset preparation
* ⚗️ Molecular descriptor analysis
* 🔬 Molecular docking
* 📊 Docking-score comparison
* 🧮 Physicochemical property analysis
* 💊 Drug-likeness assessment
* 🧪 ADMET-oriented profiling
* 🏆 Candidate prioritization

A library of **257 small molecules** was processed and evaluated against **four selected protein structures**:

| Target   | Structure |
| -------- | --------- |
| Target 1 | `1NEN`    |
| Target 2 | `1Y8P`    |
| Target 3 | `2H89`    |
| Target 4 | `6C12`    |

The objective is to use a reproducible computational workflow to identify molecules showing favorable predicted binding characteristics and suitable drug-like properties for further investigation.

> **Important:** This is a computational research project. Docking scores and predicted ADMET properties are hypotheses for further experimental investigation and do not establish biological activity, therapeutic efficacy, or clinical suitability.

---

# 🎯 Objectives

The major objectives of this project are:

1. Collect and organize protein structures relevant to SDH-related disorders.
2. Prepare protein structures for molecular docking.
3. Prepare a small-molecule library containing 257 compounds.
4. Generate standardized ligand representations.
5. Convert ligand structures into docking-compatible formats.
6. Perform molecular docking against selected protein targets.
7. Compare predicted binding affinities across compounds and targets.
8. Identify high-priority candidate molecules.
9. Analyze physicochemical and drug-likeness properties.
10. Evaluate computational ADMET/toxicity-related predictions.
11. Integrate docking and molecular-property information.
12. Generate a ranked candidate list for future experimental validation.

---

# 🧬 Scientific Background

## Succinate Dehydrogenase and SDH-Related Disorders

Succinate dehydrogenase (SDH) is a mitochondrial enzyme complex that participates in both:

* the **tricarboxylic acid (TCA) cycle**, and
* the **electron transport chain**.

The SDH complex contributes to the conversion of succinate to fumarate while transferring electrons through the respiratory chain.

Alterations in SDH-associated proteins can disrupt cellular metabolism and contribute to abnormal succinate accumulation and downstream metabolic effects.

Because SDH-related dysfunction can involve structurally and functionally important protein components, computational structural biology can be used as an initial approach for investigating potential small-molecule interactions.

---

# 🔬 Research Question

> **Can computational molecular docking and molecular-property analysis be used to prioritize small molecules with potentially favorable interactions against selected SDH-related protein targets?**

This project addresses this question through a multi-stage computational workflow.

---

# 🧪 Project Scope

The project focuses on **in-silico candidate prioritization**.

The workflow does **not** claim to:

* prove therapeutic efficacy,
* establish clinical safety,
* confirm biological activity,
* replace laboratory experiments,
* replace clinical trials,
* or provide medical treatment recommendations.

Instead, the project provides a computational screening framework that can be used to identify candidates for subsequent investigation.

---

# 🧰 Technologies & Tools

| Category                    | Technology / Tool                               |
| --------------------------- | ----------------------------------------------- |
| Programming                 | Python                                          |
| Molecular Informatics       | RDKit                                           |
| Molecular Docking           | AutoDock Vina                                   |
| Molecular Structures        | PDB / PDBQT                                     |
| Data Processing             | Pandas                                          |
| Numerical Analysis          | NumPy                                           |
| Visualization               | Matplotlib                                      |
| Interactive Analysis        | Jupyter Notebook                                |
| Environment                 | Conda                                           |
| Version Control             | Git / GitHub                                    |
| Molecular Property Analysis | Computational property / ADMET prediction tools |

---

# 📊 Dataset

## Ligand Library

The project contains:

**257 small molecules**

The original ligand collection was provided as an SDF dataset:

```text
drug_like_molecules.sdf
```

The molecules were processed and standardized for downstream computational analysis.

A ligand-to-SMILES mapping was generated containing:

```text
Ligand
Chemical_Name
SMILES
```

Example:

| Ligand        | Chemical Name       | SMILES        |
| ------------- | ------------------- | ------------- |
| `Ligand_0001` | 3-methylpentane     | `CCC(C)CC`    |
| `Ligand_0002` | 2,4-dimethylpentane | `CC(C)CC(C)C` |
| `Ligand_0003` | 1-pentene           | `C=CCCC`      |
| `Ligand_0004` | cyclohexene         | `C1=CCCCC1`   |
| `Ligand_0005` | 1,4-pentadiene      | `C=CCC=C`     |

The complete ligand mapping is stored in:

```text
Analysis/All_Ligands_SMILES.csv
```

---

# 🧬 Protein Targets

Four protein structures were prepared for docking:

```text
1NEN
1Y8P
2H89
6C12
```

The repository separates original protein structures from docking-ready receptor structures.

### Original structures

```text
Data/Proteins/
```

### Prepared receptor structures

```text
Data/PDBQT_Proteins/
```

Prepared receptors include:

```text
1NEN_receptor.pdbqt
1Y8P_receptor.pdbqt
2H89_receptor.pdbqt
6C12_receptor.pdbqt
```

---

# 🧪 Scientific Workflow

The complete computational workflow can be summarized as:

```text
                    ┌─────────────────────────┐
                    │  Protein Target Data    │
                    │  1NEN / 1Y8P / 2H89    │
                    │        / 6C12           │
                    └────────────┬────────────┘
                                 │
                                 ▼
                    ┌─────────────────────────┐
                    │ Protein Structure       │
                    │ Preparation             │
                    │ Cleaning + Conversion   │
                    └────────────┬────────────┘
                                 │
                                 ▼
                    ┌─────────────────────────┐
                    │ Docking-ready Receptors │
                    │          PDBQT           │
                    └────────────┬────────────┘
                                 │
                                 │
                                 │
┌──────────────────────┐         │
│ 257 Small Molecules  │         │
│      SDF Library     │         │
└──────────┬───────────┘         │
           │                     │
           ▼                     │
┌──────────────────────┐         │
│ Ligand Processing    │         │
│                      │         │
│ • Structure parsing  │         │
│ • SMILES extraction  │         │
│ • Standardization    │         │
└──────────┬───────────┘         │
           │                     │
           ▼                     │
┌──────────────────────┐         │
│ Ligand PDB/PDBQT     │         │
│ Preparation          │         │
└──────────┬───────────┘         │
           │                     │
           └──────────┬──────────┘
                      │
                      ▼
             ┌─────────────────┐
             │ Molecular       │
             │ Docking         │
             │ AutoDock Vina   │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │ Docking Scores  │
             │ kcal/mol        │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │ Cross-target    │
             │ Comparison      │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │ Top Candidate   │
             │ Selection       │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │ Physicochemical │
             │ Properties      │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │ Drug-likeness   │
             │ & ADMET         │
             │ Profiling       │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │ Final Candidate │
             │ Prioritization  │
             └─────────────────┘
```

---

# 🔬 Step 1 — Protein Structure Preparation

Protein structures were collected in PDB format and processed to produce docking-compatible receptor structures.

The preparation workflow included structural cleaning and conversion into PDBQT format.

Prepared receptors:

```text
1NEN_receptor.pdbqt
1Y8P_receptor.pdbqt
2H89_receptor.pdbqt
6C12_receptor.pdbqt
```

The PDBQT format contains structural and partial-charge information required for AutoDock Vina docking calculations.

---

# 🧪 Step 2 — Ligand Dataset Preparation

The original ligand library was supplied as:

```text
Data/Ligands/Raw/drug_like_molecules.sdf
```

The dataset contains:

```text
257 molecules
```

RDKit was used to parse molecular structures and extract chemical representations.

The resulting dataset was converted into a structured CSV representation containing:

```text
Ligand
Chemical_Name
SMILES
```

Output:

```text
Analysis/All_Ligands_SMILES.csv
```

---

# ⚗️ Step 3 — Molecular Representation

SMILES representations provide a compact representation of molecular connectivity.

The project generated standardized molecular representations that enabled downstream:

* descriptor calculation,
* property analysis,
* ligand identification,
* structure comparison,
* and computational screening.

---

# 🔬 Step 4 — Ligand Docking Preparation

The ligands were converted into docking-compatible PDBQT files.

The ligand directory contains:

```text
Data/Ligands/
│
├── Raw/
├── PDB/
├── PDBQT/
└── Properties/
```

The PDBQT ligand files were used as inputs for molecular docking.

---

# 🧬 Step 5 — Molecular Docking

Molecular docking was performed using:

**AutoDock Vina**

The docking procedure estimates favorable ligand binding poses and provides predicted binding affinity scores.

Docking affinity is reported in:

```text
kcal/mol
```

More negative predicted affinity values generally indicate stronger predicted binding under the docking model.

> **Important:** Docking affinity is a computational scoring estimate and should not be interpreted as experimentally measured binding affinity.

---

# 📊 Step 6 — Multi-Target Docking

The 257-molecule library was evaluated against four receptor structures.

The resulting docking analyses were organized by target:

```text
Docking/
├── 1NEN/
├── 1Y8P/
├── 2H89/
└── 6C12/
```

The resulting target-specific docking files are stored in:

```text
Results/
```

---

# 🏆 Step 7 — Candidate Ranking

Docking results were sorted according to predicted affinity.

The strongest-scoring molecules were selected as candidates for further analysis.

For example, the current 6C12 docking results identified several molecules with relatively favorable predicted docking scores.

### Top candidates identified for 6C12

| Rank | Ligand        | Predicted Affinity (kcal/mol) |
| ---: | ------------- | ----------------------------: |
|    1 | `Ligand_0241` |                      `-8.188` |
|    2 | `Ligand_0169` |                      `-7.763` |
|    3 | `Ligand_0256` |                      `-7.679` |
|    4 | `Ligand_0022` |                      `-7.507` |
|    5 | `Ligand_0159` |                      `-7.476` |
|    6 | `Ligand_0240` |                      `-7.338` |
|    7 | `Ligand_0257` |                      `-7.211` |
|    8 | `Ligand_0244` |                      `-7.173` |
|    9 | `Ligand_0143` |                      `-7.118` |
|   10 | `Ligand_0021` |                      `-7.052` |

These values represent **predicted docking scores**, not experimentally measured binding constants.

---

# 🧪 Step 8 — Cross-Target Analysis

Docking results from multiple targets were combined to facilitate comparison.

The combined dataset is:

```text
Results/Combined_Docking_Results.csv
```

This enables analysis of:

* target-specific binding,
* ligand-specific performance,
* cross-target affinity,
* candidate consistency,
* and prioritization of molecules for further study.

---

# ⚠️ Docking Quality Control

Not every docking result should automatically be interpreted as a valid biological result.

During analysis, some target-specific results showed unusual score distributions.

For example, some entries for:

```text
2H89
1NEN
```

returned docking values of:

```text
0.0
```

Such results should be treated as **quality-control flags rather than strong binding evidence**.

Possible causes can include:

* docking configuration issues,
* receptor preparation problems,
* incorrect search space,
* ligand/receptor compatibility problems,
* failed docking runs,
* or parsing/output issues.

Therefore, zero-valued docking results are **not interpreted as biologically meaningful binding scores** in this project.

Similarly, unusual or weak docking distributions should be investigated before making biological conclusions.

---

# 🧮 Step 9 — Molecular Property Analysis

Top-ranked candidates were further analyzed using molecular descriptors.

The analyzed properties include:

### Molecular Size

* Molecular weight
* Heavy atom count
* Aromatic heavy atom count

### Molecular Topology

* Fraction Csp3
* Rotatable bonds
* Ring count

### Hydrogen Bonding

* H-bond acceptors
* H-bond donors

### Polarity

* TPSA
* Molecular refractivity

### Lipophilicity

* XLOGP3
* WLOGP
* MLOGP
* Silicos-IT LogP
* Consensus LogP

### Solubility

* ESOL LogS
* Ali LogS
* Silicos-IT LogSw

These descriptors provide a broader view of the chemical properties of candidate molecules.

---

# 💊 Step 10 — Drug-Likeness Analysis

Candidate compounds were evaluated using commonly used drug-likeness rules and filters.

The analysis includes:

* Lipinski rule violations
* Ghose violations
* Veber violations
* Egan violations
* Muegge violations
* Bioavailability score
* PAINS alerts
* Brenk alerts
* Lead-likeness violations
* Synthetic accessibility

These properties are used for **candidate prioritization**, not as definitive evidence of drug suitability.

---

# 🧪 Step 11 — ADMET-Oriented Profiling

The prioritized compounds were also evaluated using computational ADMET-related predictions.

The analyzed categories include, where available:

### Absorption

* GI absorption
* Caco-2 permeability
* PAMPA-related predictions
* HIA-related predictions

### Distribution

* BBB permeability
* Plasma protein binding
* Volume of distribution

### Metabolism

Predicted interactions involving:

* CYP1A2
* CYP2C19
* CYP2C9
* CYP2D6
* CYP3A4
* CYP2B6
* CYP2C8

### Transport

Potential interactions with:

* P-glycoprotein
* BCRP
* BSEP
* OATP transporters
* MRP transporters

### Toxicity

Computational toxicity-related predictions include categories such as:

* hERG
* hepatotoxicity
* nephrotoxicity
* neurotoxicity
* genotoxicity
* carcinogenicity
* skin sensitization
* aquatic toxicity

> These predictions are **in-silico estimates** and require experimental validation.

---

# 🧠 Candidate Prioritization Strategy

Candidate selection is not based solely on docking affinity.

The overall prioritization concept is:

```text
                 Docking Affinity
                       │
                       ▼
              ┌────────────────┐
              │ Binding Score  │
              └───────┬────────┘
                      │
                      ▼
          ┌────────────────────────┐
          │ Molecular Properties   │
          └────────────┬───────────┘
                       │
                       ▼
          ┌────────────────────────┐
          │ Drug-likeness Filters  │
          └────────────┬───────────┘
                       │
                       ▼
          ┌────────────────────────┐
          │ ADMET / Toxicity       │
          │ Predictions            │
          └────────────┬───────────┘
                       │
                       ▼
             ┌──────────────────┐
             │ Final Candidate  │
             │ Prioritization   │
             └──────────────────┘
```

A strong candidate should ideally demonstrate a combination of:

* favorable predicted docking affinity,
* acceptable molecular properties,
* reasonable drug-likeness,
* acceptable predicted solubility,
* manageable ADMET predictions,
* limited structural alerts,
* and reasonable synthetic accessibility.

---

# 📁 Repository Structure

```text
PROJECT-AI-BASED-DRUG-TARGET-IDENTIFICATION/
│
├── 📁 Analysis/
│   ├── All_Ligands_SMILES.csv
│   └── Top10_Final.csv
│
├── 📁 Data/
│   │
│   ├── 📁 Clean_Proteins/
│   │
│   ├── 📁 Datasets/
│   │
│   ├── 📁 Ligands/
│   │   ├── Raw/
│   │   ├── PDB/
│   │   ├── PDBQT/
│   │   └── Properties/
│   │
│   ├── 📁 PDBQT_Proteins/
│   │   ├── 1NEN_receptor.pdbqt
│   │   ├── 1Y8P_receptor.pdbqt
│   │   ├── 2H89_receptor.pdbqt
│   │   └── 6C12_receptor.pdbqt
│   │
│   ├── 📁 Proteins/
│   │
│   ├── 📁 Results/
│   │
│   └── 📁 Structures/
│
├── 📁 Docking/
│   ├── 1NEN/
│   ├── 1Y8P/
│   ├── 2H89/
│   └── 6C12/
│
├── 📁 Figures/
│
├── 📁 Notebooks/
│
├── 📁 Results/
│   ├── 1NEN_results.csv
│   ├── 1Y8P_results.csv
│   ├── 2H89_results.csv
│   ├── 6C12_results.csv
│   └── Combined_Docking_Results.csv
│
├── 📁 Report/
│
├── 📄 requirements.txt
├── 📄 .gitignore
└── 📄 README.md
```

> Repository contents may evolve as the project is expanded and additional analyses are added.

---

# 🧪 Reproducibility

The project is designed around a reproducible computational workflow.

The major stages are:

```text
Raw Data
   ↓
Structure Preparation
   ↓
Molecular Representation
   ↓
Docking Preparation
   ↓
Molecular Docking
   ↓
Docking Result Processing
   ↓
Candidate Ranking
   ↓
Molecular Property Analysis
   ↓
ADMET Profiling
   ↓
Candidate Prioritization
```

All important intermediate datasets and analysis outputs should be retained where practical.

---

# 💻 Installation

## 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
cd YOUR-REPOSITORY
```

---

## 2. Create a Conda Environment

```bash
conda create -n drug_discovery python=3.11
```

Activate the environment:

```bash
conda activate drug_discovery
```

---

## 3. Install Python Dependencies

```bash
pip install -r requirements.txt
```

Recommended core Python packages include:

```text
numpy
pandas
matplotlib
seaborn
rdkit
jupyter
scikit-learn
```

> Add only the packages actually required by the notebooks/scripts in the final repository.

---

# 🧰 External Software

## AutoDock Vina

AutoDock Vina is used for molecular docking and scoring.

The executable should be available in the system environment or configured through the project scripts.

---

# ▶️ Running the Project

A typical execution sequence is:

### Step 1 — Prepare Ligand Data

Run the ligand-processing notebook or script.

Generate:

```text
Analysis/All_Ligands_SMILES.csv
```

---

### Step 2 — Prepare Receptors

Prepare the selected protein structures and generate:

```text
Data/PDBQT_Proteins/
```

---

### Step 3 — Prepare Ligands

Generate docking-compatible ligand structures:

```text
Data/Ligands/PDBQT/
```

---

### Step 4 — Perform Docking

Run AutoDock Vina against the prepared receptor structures.

Docking outputs are organized under:

```text
Docking/
```

---

### Step 5 — Process Docking Results

Generate target-specific result files:

```text
Results/
├── 1NEN_results.csv
├── 1Y8P_results.csv
├── 2H89_results.csv
└── 6C12_results.csv
```

---

### Step 6 — Combine Results

Generate:

```text
Results/Combined_Docking_Results.csv
```

---

### Step 7 — Rank Candidates

Generate:

```text
Analysis/Top10_Final.csv
```

---

### Step 8 — Analyze Molecular Properties

Evaluate:

* molecular weight,
* lipophilicity,
* TPSA,
* hydrogen bonding,
* solubility,
* drug-likeness,
* structural alerts,
* and ADMET-related predictions.

---

# 📈 Current Computational Results

The current workflow successfully processed:

```text
257 small molecules
```

against:

```text
4 protein structures
```

with docking results generated for the evaluated targets.

One of the strongest observed docking profiles in the current dataset was obtained for:

```text
6C12
```

The leading predicted docking score was:

```text
Ligand_0241
-8.188 kcal/mol
```

Other highly ranked compounds included:

```text
Ligand_0169    -7.763 kcal/mol
Ligand_0256    -7.679 kcal/mol
Ligand_0022    -7.507 kcal/mol
Ligand_0159    -7.476 kcal/mol
Ligand_0240    -7.338 kcal/mol
Ligand_0257    -7.211 kcal/mol
Ligand_0244    -7.173 kcal/mol
Ligand_0143    -7.118 kcal/mol
Ligand_0021    -7.052 kcal/mol
```

The complete ranking is available in:

```text
Analysis/Top10_Final.csv
```

---

# 🔎 Example Candidate Profile

The highest-ranked compound for the current 6C12 analysis was:

```text
Ligand_0241
```

Chemical name:

```text
Bendroflumethiazide
```

Predicted docking affinity:

```text
-8.188 kcal/mol
```

The computational property analysis included:

* Molecular weight
* TPSA
* Lipophilicity
* Solubility
* Drug-likeness
* Structural alerts
* ADMET-related predictions
* Synthetic accessibility

This integrated analysis is intended to prevent selection based solely on docking score.

---

# 📊 Data Analysis Outputs

Important generated files include:

### Ligand Mapping

```text
Analysis/All_Ligands_SMILES.csv
```

Contains the ligand library and molecular identifiers.

### Candidate Ranking

```text
Analysis/Top10_Final.csv
```

Contains the current prioritized docking candidates.

### Combined Docking Results

```text
Results/Combined_Docking_Results.csv
```

Contains combined docking results across the evaluated receptor structures.

---

# 📚 Scientific Interpretation

The project follows a **multi-parameter candidate prioritization strategy**.

A compound with a favorable docking score is not automatically considered a successful drug candidate.

Instead, computational prioritization considers:

```text
Binding
   +
Molecular Properties
   +
Drug-likeness
   +
Solubility
   +
ADMET
   +
Toxicity Predictions
   +
Synthetic Accessibility
```

This approach reduces dependence on a single computational metric.

---

# ⚠️ Limitations

This project has several important limitations.

### 1. Docking is Predictive

Molecular docking predicts possible ligand binding modes and approximate scoring values.

It does not experimentally confirm binding.

### 2. Protein Flexibility

Most docking workflows treat the receptor as relatively rigid compared with the flexibility present in biological systems.

### 3. Scoring-Function Limitations

Docking scores are approximate and depend on the scoring function and docking configuration.

### 4. ADMET Predictions Are Computational

Predicted pharmacokinetic and toxicity properties should not be interpreted as experimentally confirmed safety data.

### 5. No Experimental Validation

The current project does not include:

* biochemical assays,
* cell-based assays,
* animal studies,
* or clinical studies.

### 6. Target-Specific Docking Quality

Some docking outputs require additional quality-control investigation, particularly results showing unexpected zero-valued or otherwise abnormal scores.

### 7. Binding Affinity ≠ Therapeutic Activity

A favorable predicted docking score does not prove:

```text
Target inhibition
        ↓
Cellular activity
        ↓
Disease modification
        ↓
Therapeutic efficacy
```

Experimental validation is required to establish these relationships.

---

# 🚀 Future Improvements

The project can be extended with additional computational analyses.

## Structural Validation

* Redocking of known/reference ligands
* RMSD-based pose validation
* Binding-site analysis
* Protein-ligand interaction analysis

## Advanced Molecular Modeling

* Molecular dynamics simulations
* MM/PBSA or MM/GBSA calculations
* Binding free-energy estimation

## Machine Learning

Future versions could incorporate:

* molecular fingerprints,
* molecular descriptors,
* docking scores,
* supervised learning,
* clustering,
* similarity-based screening,
* and candidate classification.

## Chemical Prioritization

Additional filtering can include:

* scaffold analysis,
* chemical diversity,
* synthetic accessibility,
* structural alerts,
* and analog searching.

---

# 🧠 Potential AI / Machine-Learning Extension

A future AI-assisted version of the workflow could represent each compound using molecular fingerprints and descriptors.

For example:

```text
Molecular Structure
        ↓
SMILES
        ↓
RDKit Descriptors
        ↓
Molecular Fingerprints
        ↓
Docking Score
        ↓
ADMET Features
        ↓
Machine Learning Model
        ↓
Candidate Ranking
```

Possible models include:

* Random Forest
* Logistic Regression
* Support Vector Machine
* Gradient Boosting
* Neural Networks

Such models would require an appropriately labeled training dataset and rigorous validation before biological interpretation.

> **Current project scope:** The present repository should not claim that a machine-learning model was trained unless a validated ML model and corresponding training/evaluation workflow are actually included.

---

# 📌 Research Significance

This project demonstrates how computational methods can be integrated into an early-stage drug-discovery workflow.

The project combines:

```text
Bioinformatics
      +
Structural Biology
      +
Chemoinformatics
      +
Molecular Docking
      +
Drug-likeness Analysis
      +
ADMET Prediction
      ↓
Computational Candidate Prioritization
```

The workflow can help reduce the number of compounds requiring subsequent experimental investigation by identifying candidates that satisfy multiple computational criteria.

---

# 🧬 Reproducible Research Philosophy

The repository is structured to keep:

* raw input data,
* processed structures,
* docking inputs,
* docking outputs,
* analysis datasets,
* notebooks,
* figures,
* and final results

separated and traceable.

This structure makes it easier to:

* reproduce analyses,
* inspect intermediate results,
* modify individual pipeline stages,
* add additional protein targets,
* add new ligands,
* and extend the workflow with machine-learning methods.

---

# 📂 File Organization Philosophy

```text
Data/
    Raw and processed biological/chemical data

Analysis/
    Processed tables and analytical datasets

Docking/
    Molecular docking inputs and outputs

Figures/
    Generated visualizations

Notebooks/
    Reproducible computational analyses

Results/
    Final processed results

Report/
    Supporting project documentation
```

---

# 🔬 Computational Pipeline Summary

```text
                 ┌────────────────────┐
                 │ Protein Structures │
                 └─────────┬──────────┘
                           │
                           ▼
                 ┌────────────────────┐
                 │ Protein Preparation│
                 └─────────┬──────────┘
                           │
                           ▼
                 ┌────────────────────┐
                 │ Receptor PDBQT     │
                 └─────────┬──────────┘
                           │
                           │
                           ▼
┌────────────────────────────────────────────┐
│              257 Molecule Library          │
└───────────────────────┬────────────────────┘
                        │
                        ▼
              ┌──────────────────┐
              │ RDKit Processing │
              └────────┬─────────┘
                       │
                       ▼
              ┌──────────────────┐
              │ Ligand PDB/PDBQT│
              └────────┬─────────┘
                       │
                       ▼
              ┌──────────────────┐
              │ AutoDock Vina    │
              │ Molecular Docking│
              └────────┬─────────┘
                       │
                       ▼
              ┌──────────────────┐
              │ Docking Scores   │
              └────────┬─────────┘
                       │
                       ▼
              ┌──────────────────┐
              │ Candidate Ranking│
              └────────┬─────────┘
                       │
                       ▼
        ┌─────────────────────────────┐
        │ Molecular Property Analysis │
        └──────────────┬──────────────┘
                       │
                       ▼
              ┌──────────────────┐
              │ Drug-likeness    │
              └────────┬─────────┘
                       │
                       ▼
              ┌──────────────────┐
              │ ADMET Profiling  │
              └────────┬─────────┘
                       │
                       ▼
              ┌──────────────────┐
              │ Final Candidate  │
              │ Prioritization   │
              └──────────────────┘
```

---

# 📌 Key Project Statistics

| Metric                    | Value                              |
| ------------------------- | ---------------------------------- |
| Small molecules screened  | **257**                            |
| Protein targets evaluated | **4**                              |
| Primary docking software  | **AutoDock Vina**                  |
| Molecular toolkit         | **RDKit**                          |
| Main language             | **Python**                         |
| Docking output            | **kcal/mol**                       |
| Main analysis environment | **Jupyter / Conda**                |
| Final candidate ranking   | **Top 10**                         |
| Cross-target result file  | **`Combined_Docking_Results.csv`** |

---

# 👩‍🔬 Skills Demonstrated

This project demonstrates practical experience in:

## Bioinformatics

* Protein structure handling
* Molecular structure processing
* Biological data organization

## Computational Chemistry

* Molecular docking
* Ligand preparation
* Receptor preparation
* Molecular descriptors
* Drug-likeness analysis

## Chemoinformatics

* SMILES processing
* Molecular property calculation
* Chemical structure representation
* Candidate prioritization

## Data Science

* CSV processing
* Data cleaning
* Ranking
* Comparative analysis
* Data visualization

## Programming

* Python
* Pandas
* NumPy
* RDKit
* Jupyter Notebook

## Research Skills

* Reproducible computational workflows
* Scientific data interpretation
* Computational hypothesis generation
* Critical evaluation of prediction limitations

---

# 📖 Reproducibility Checklist

* [x] Protein structures available
* [x] Protein structures prepared
* [x] Receptor PDBQT files generated
* [x] Ligand source dataset available
* [x] Ligand structures processed
* [x] Ligand PDBQT files generated
* [x] Docking performed
* [x] Docking outputs generated
* [x] Docking results combined
* [x] Top candidates ranked
* [x] Molecular properties analyzed
* [x] Drug-likeness evaluated
* [x] ADMET predictions reviewed
* [x] Quality-control issues identified
* [x] Results stored in structured files
* [x] Analysis notebooks preserved

---

# ⚠️ Disclaimer

This repository contains computational research work intended for **educational and research purposes**.

The predictions presented here are generated using computational models and should not be interpreted as:

* clinical recommendations,
* medical advice,
* experimentally confirmed drug activity,
* proof of therapeutic efficacy,
* or evidence of clinical safety.

All prioritized compounds require appropriate experimental validation before any biological or therapeutic conclusions can be made.

---

# 📜 License

This project is intended for academic and research use.

A suitable open-source license can be added to the repository depending on the intended use and distribution requirements.

---

# 👩‍💻 Author

**Sofiya Chavarekar**

B.Tech Bioengineering (Bioinformatics)
VIT Bhopal University

---

# ⭐ Project Summary

> **A computational drug-discovery pipeline integrating ligand processing, protein structure preparation, molecular docking, chemoinformatics, drug-likeness analysis, and ADMET-oriented profiling to prioritize small-molecule candidates against selected SDH-related protein targets.**

---

<p align="center">

### 🧬 From Molecular Structure → Docking → Properties → Candidate Prioritization

**Computational Drug Discovery • Bioinformatics • Structural Biology • Chemoinformatics**

</p>
