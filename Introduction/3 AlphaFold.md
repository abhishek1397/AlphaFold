# What is AlphaFold?

**AlphaFold** is Google DeepMind’s breakthrough artificial intelligence system designed to solve the long-standing problem of protein structure prediction. It predicts the 3D structure of proteins from their amino acid sequences with remarkable accuracy and is widely used by researchers around the world.

## How AlphaFold Works

AlphaFold2 is a multicomponent **AI system** that uses **machine learning** to predict a protein’s 3D structure from its **primary amino acid sequence**.

- **Machine learning** allows AI to learn patterns from vast datasets and apply them to make accurate predictions on new data.
- AlphaFold2 employs an **artificial neural network**—a collection of interconnected simulated nodes that adapt based on learned patterns.
- With multiple layers of nodes, AlphaFold2 qualifies as a **deep learning** system, capable of identifying complex patterns in protein folding.

## Key Characteristics

- AlphaFold is **not a homology modeling tool**—it does not rely on template structures.
- It can accurately predict **previously unknown protein folds**.
- The system's detailed architecture and performance can be found in the [AlphaFold paper (Jumper et al., 2021)](https://www.nature.com/articles/s41586-021-03819-2), and its implementation is available as [open-source code](https://github.com/deepmind/alphafold).

> **Note:** AlphaFold represents a major leap forward in structural biology, helping close the gap between known protein sequences and solved 3D structures.

---

## How AlphaFold2 Solves the Structure Prediction Problem

AlphaFold2 tackles the protein structure prediction problem using deep learning trained on experimentally determined protein structures.

### Training Data

- **Source:** AlphaFold2 was trained using data from the **Protein Data Bank (PDB)** — a public repository of all experimentally resolved macromolecular structures, currently holding over **215,000 entries**.
- **Input:** Each entry includes the 3D structure and its corresponding amino acid sequence, which were used to train the AlphaFold2 neural network.

### Prediction Process

- AlphaFold2 begins with a **novel amino acid sequence**.
- It performs **multiple sequence alignment (MSA)** to compare the input with evolutionarily related proteins.
- By identifying **correlated mutations** (changes that occur together over time), AlphaFold2 infers which residues are likely to be **spatially close** in the 3D structure.
- Within **minutes**, AlphaFold2 generates a 3D structural prediction, even for previously unseen proteins.

> **Note:** AlphaFold2 may or may not use existing protein structures as templates. It is capable of accurate prediction without them.

### Confidence Metrics

AlphaFold2 provides **confidence scores** to help interpret the accuracy of its predictions:

- **pLDDT (Predicted Local Distance Difference Test):** Confidence in individual residue positions.
- **pTM (Predicted TM-score):** Confidence in overall structure similarity.
- **PAE (Predicted Aligned Error):** Confidence in relative positions of residue pairs.

These scores highlight regions where predictions are less certain, supporting **critical scientific interpretation** of results.

![alphafold_solve](https://github.com/user-attachments/assets/514fca44-e457-4187-9eb0-79c197a6d8a8)
*Figure 1: [From Sequence to Structure. AlphaFold2 takes the protein sequence and, in minutes, predicts their 3D structure]*  

--- 

## AlphaFold Milestones

In 2020, **AlphaFold2** gained international recognition after winning the prestigious **Critical Assessment of Structure Prediction (CASP14)**. This challenge tests the ability of computational methods to predict protein structures that have been experimentally determined but not yet published. AlphaFold2's predictions were so accurate that CASP organizers declared the structure prediction problem "largely solved for single proteins."

AlphaFold2 is available as an **open-source program**. It can be installed locally on high-performance systems or accessed via web services like **Google Colab** using **AlphaFold** or **ColabFold** notebooks. Additionally, the **AlphaFold Protein Structure Database (AFDB)** provides precomputed structures for nearly all (~200 million) proteins in UniProt.

Since its public release in 2021, AlphaFold2 has been widely adopted by researchers. By the end of 2023:
- The original paper had received **over 15,000 citations**.
- The AFDB had attracted **1.65 million unique users** from **180+ countries**.
- The database had been **downloaded over 22,000 times** worldwide.

---

# AlphaFold2

### Overview
AlphaFold2 is a breakthrough deep learning model designed to predict protein structures. Its capabilities and constraints are deeply tied to the data used during its training.

## ✅ What AlphaFold2 Can Do

* **Single-Chain Protein Structure Prediction**:
  Originally trained on individual protein chains from the Protein Data Bank (PDB), AlphaFold2 demonstrates high accuracy in predicting single-chain structures.

* **Protein-Protein Complexes (AlphaFold-Multimer)**:
  An extended version, **AlphaFold-Multimer** (Evans et al., 2022), was trained to predict:

  * **Homo-multimers** (identical protein chains, e.g., dimers, hexamers — identical chains)
  * **Hetero-multimers** (protein complexes made of different chains)

* **Novel Structure Prediction**:
  AlphaFold2 is not limited to replicating known protein structures. Independent studies (Bordin et al., 2023; Barrio-Hernandez et al., 2023; Durairaj et al., 2023) have demonstrated that it can predict entirely **novel protein folds**, previously unseen in the PDB.


## ⚠️ Limitations

* **Training Data Scope**:
  AlphaFold2 was trained using only **protein structures** from the PDB, excluding other biological components like:

  * Small molecules
  * Nucleic acids

  This limits its ability to predict structures involving these non-protein elements.

* **Limited Prediction of Dynamic and Disordered Regions**:
  AlphaFold2 struggles to predict disordered or dynamic regions that do not conform to a fixed structure in nature, as these regions do not have a single stable conformation.



## ⚠️ What AlphaFold2 Struggles With

* **Sensitivity to Point Mutations**:
  AlphaFold2 is not sensitive to point mutations that alter a single residue in the protein sequence. This limitation arises from:

  * A **lack of data** on the effects of variations.
  * AlphaFold2’s focus on identifying **patterns** rather than calculating **physical forces**.

  As a result, AlphaFold2 may not accurately predict structures affected by point mutations or other sequence variations, particularly in cases like **immune system molecules** (e.g., antibodies) where sequences are highly variable.

* **Prediction of “Orphan” Proteins**:
  AlphaFold2 relies on **sequence relationships** to predict protein structures. For “orphan” proteins — those with few or no close relatives — the lack of sufficient sequence data hampers AlphaFold2's ability to generate accurate predictions. When related sequences are rare or lack known structures in the PDB, the predictions often come with low confidence scores.

* **Dynamic Conformational Changes**:
  AlphaFold2 is designed to predict **static** protein structures, which are essentially **structural snapshots**. While many proteins undergo structural changes to perform their biological functions, these conformational shifts are underrepresented in the PDB. As a result:

  * AlphaFold2 does not capture these dynamic changes by default.
  * However, through **advanced techniques**, it is possible to force AlphaFold2 to predict alternative conformations (see section: *“Advanced modelling and applications of predicted protein structures”*).


![Hexokinase Conformations](https://ftp.ebi.ac.uk/pub/training/2024/On-demand/PDBe_KB_2.gif)
[Figure 2.](https://ftp.ebi.ac.uk/pub/training/2024/On-demand/PDBe_KB_2.gif) One of AlphaFold’s limitations is that it is not aware of molecules that bind to proteins, which can affect the protein’s 3D structure. Hexokinase (Q96Y14) adopts distinct conformations in the presence (orange, left) and absence (green, right) of sugar. Notably, AlphaFold’s structure prediction aligns with the sugar-free state (as could be seen both visually and via RMSD value).

---

## ⚠️ What AlphaFold2 Can’t Do

* **Interaction with Non-Protein Molecules**:
  AlphaFold2 is **not aware** of interactions with molecules outside of proteins, such as:

  * **Nucleic acids**
  * **Small molecule co-factors**
  * **Ions**
  * **Other non-protein components**

  While AlphaFold2 was not designed to model post-translational modifications or free nucleic acid structures, it may still predict **ligand- or ion-bound protein forms**, even in the absence of the actual ligand/ion.

* **Membrane Protein Modeling**:
  AlphaFold2 does not account for the **membrane plane** and thus cannot correctly model:

  * The **relative orientations** of trans-membrane domains.
  * The positioning of other protein domains in membrane proteins.

  However, AlphaFold2 provides **confidence scores** to alert users to uncertainties, with issues in membrane protein modeling often reflected in the predicted aligned error (PAE) score.

---

| AlphaFold2 Predicts                              | AlphaFold2 Struggles to Predict                         | AlphaFold2 Doesn’t Predict                                      |
|--------------------------------------------------|---------------------------------------------------------|------------------------------------------------------------------|
| Single protein chains                            | Multiple conformations for the same sequence            | Protein-DNA and protein-RNA complexes                           |
| Protein multimers                                | Effects of point mutations                              | Nucleic acid structure                                           |
| Multisubunit protein-protein complexes           | Antigen-antibody interactions                           | Post-translational modifications                                |
|                                                  |                                                         | Ligand and ion binding (accurately and explicitly)              |
|                                                  |                                                         | Membrane plane for transmembrane domains                        |

