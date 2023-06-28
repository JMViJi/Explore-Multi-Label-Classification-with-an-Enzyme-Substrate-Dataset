# Multi-Label Classification with an Enzyme Substrate 

## Introduction
The study of enzymes, specialized proteins that catalyze biochemical reactions, is crucial for understanding the mechanisms behind many biological processes. One of the most challenging tasks in bioinformatics is to predict the enzymes acting on a specific substrate from sequence or structure data. In this Kaggle competition, we tackle the problem of multi-label classification of enzyme substrates from a dataset of molecular features.

### Problem Summary
In this Kaggle competition, the primary task is to develop a model capable of accurately predicting the classifications of enzymes, specifically EC1 and EC2. These are not simply classifications, but rather represent specific types of enzymes that interact with substrates in unique ways. Our predictions will be made for each identifier in the test set, based on a collection of molecular features.

To understand this task more profoundly, it's important to grasp the biological basis behind it. Enzymes are specialized proteins that accelerate chemical reactions within organisms. For instance, specific enzymes in your stomach aid in breaking down ingested food into smaller, usable components for your body.

A crucial characteristic of enzymes is that they interact with particular substrates in a manner reminiscent of a key fitting into a lock. In this analogy, the enzyme represents the key, while the substrate represents the lock. Intriguingly, this interaction isn't exclusive — one type of enzyme can interact with multiple substrates, and a single substrate can be acted upon by several enzymes.

This unique many-to-many interaction brings about the main challenge of this competition. We are tasked to predict which type of enzyme, either EC1 or EC2, will interact with a substrate based on the substrate's specific features. In essence, our model should determine the "correct key" for each "lock" by examining the properties of the lock.

The complexity of this task arises from the need to predict multiple "keys" for each "lock", a situation that defines this as a multi-label classification problem.

As for the evaluation of submissions, the primary metric utilized is the Area Under the Receiver Operating Characteristic Curve (AUC-ROC). This metric measures how well your model can distinguish between different types of enzymes. Your model's predictions will be compared to the actual classifications, with the final score being the average AUC of each predicted column. This offers a balanced view of the model's performance across the different targets.

### Dataset
The dataset provided for this competition consists of various molecular features, including BertzCT, Chi1, Chi1n, Chi1v, Chi2n, Chi2v, Chi3v, Chi4n, EState_VSA1, EState_VSA2, ExactMolWt, FpDensityMorgan1, FpDensityMorgan2, FpDensityMorgan3, HallKierAlpha, HeavyAtomMolWt, Kappa3, MaxAbsEStateIndex, MinEStateIndex, NumHeteroatoms, PEOE_VSA10, PEOE_VSA14, PEOE_VSA6, PEOE_VSA7, PEOE_VSA8, SMR_VSA10, SMR_VSA5, SlogP_VSA3, VSA_EState9, fr_COO, fr_COO2, EC1, EC2, EC3, EC4, EC5, EC6.

### Feature Characteristics
The features provided in the dataset are a combination of various structural and physicochemical features of the molecules, such as the exact molecular weight (ExactMolWt), the number of heteroatoms (NumHeteroatoms), and various topological and electrostatic features (BertzCT, Chi1, Chi1n, etc.). Each of these features captures a unique aspect of the molecule's structure and function, and they are expected to contribute significantly to the prediction of enzyme activity.

- Identifier:

    - id: Unique Identifier.

- Molecular Descriptors (information about the size, weight, and presence of specific atoms):

    - ExactMolWt: Exact molecular weight.
    - HeavyAtomMolWt: Molecular weight of heavy atoms (excluding hydrogens).
    - NumHeteroatoms: Number of heteroatoms (atoms other than carbon and hydrogen).
  

- Connectivity and Structural Descriptors (capturing different aspects of the connectivity and complexity of the molecule):

    - BertzCT: Bertz complexity index.
    - Chi1: 1st order molecular connectivity index.
    - Chi1n: Chi1 normalized.
    - Chi1v: 1st order molecular variance connectivity index.
    - Chi2n: 2nd order molecular connectivity index.
    - Chi2v: 2nd order molecular variance connectivity index.
    - Chi3v: 3rd order molecular variance connectivity index.
    - Chi4n: 4th order molecular connectivity index, normalized.
    - HallkierAlpha: The Hall-Kier alpha value for a molecule.
    - Kappa3: Hall-Kier Kappa3 value.


- Surface Area Contribution Descriptors (provide information about the surface area contributions for specific atom type fragments within the molecule):

    - EState_VSA1, EState_VSA2: Electrotopological state.
    - PEOE_VSA10, PEOE_VSA14, PEOE_VSA6, PEOE_VSA7, PEOE_VSA8: Partial equalization of orbital electronegativity Van der Waals surface area contribution for a specific atom type.
    - SMR_VSA10, SMR_VSA5: Solvent-accessible surface area Van der Waals surface area contribution for a specific atom type.
    - SlogP_VSA3: LogP-based surface area contribution.
    - VSA_EState9: E-state fragment contribution for Van der Waals surface area calculation.


- Fingerprint Density Descriptors (represent the density or count of specific substructures in the Morgan fingerprint):

    - FpDensityMorgan1: Morgan fingerprint density for radius 1.
    - FpDensityMorgan2: Morgan fingerprint density for radius 2.
    - FpDensityMorgan3: Morgan fingerprint density for radius 3.
  

- Functional Groups:
    - fr_COO, fr_COO2: Number of carboxyl (COO) functional groups, ranging 0-8.
  

- EC Classifications:

    - EC1: Binary feature, Oxidoreductases - catalyze oxidation-reduction reactions, involving the transfer of electrons between molecules.
    - EC2: Binary feature, Transferases - transfer functional groups (e.g., methyl, acetyl, phosphoryl) between molecules.
    - EC3: Binary feature, Hydrolases - catalyze the hydrolysis (breaking of chemical bonds with water) of various substances.
    - EC4: Binary feature, Lyases - catalyze the addition or removal of groups from substrates without hydrolysis or oxidation.
    - EC5: Binary feature, Isomerases - catalyze the rearrangement of atoms within a molecule to form isomers (same molecular formula, different arrangement).
    - EC6: Binary feature, Ligases - catalyze the joining of two molecules through the formation of new chemical bonds.

### Methodology
The problem posed in this competition is a multi-label classification problem. Given the feature set provided, the methodological approach will involve the use of machine learning and/or deep learning techniques to build a model that is capable of predicting the EC1 and EC2 targets. As the model's performance is evaluated based on AUC-ROC, the methodology will also need to include strategies to maximize this metric. Lastly, as the problem involves predicting multiple labels, it may be useful to consider approaches specific to multi-label classification, such as chain classifiers or problem transformation methods.

## Usage
The project is structured as a Jupyter notebook, which provides a detailed walk-through of the code, methodology, and analysis. To use the notebook, clone the repository and run it on a Jupyter notebook environment. The required dependencies can be installed using pip:

```bash
pip install -r requirements.txt
```

## Contact
For any questions, comments, or feedback, feel free to reach out to me at josevillalbajimenez@gmail.com

## Acknowledgments
This project would not have been possible without the dataset provided for this competition. I would like to thank Kaggle for hosting this competition and providing an excellent platform for data science enthusiasts to learn and grow.
