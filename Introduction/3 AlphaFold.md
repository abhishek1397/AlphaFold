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

