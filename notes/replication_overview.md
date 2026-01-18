# Replication Overview – N400 ERP Study

This document provides a high-level overview of the replication project
prepared for an ERP course and BrainHack event.

The goal was to replicate the core N400 effect using a publicly available
EEG dataset and to understand the practical challenges of ERP preprocessing
and analysis.

---

## Original Study

Toffolo, K. K., Freedman, E. G., & Foxe, J. J. (2022).  
*Evoking the N400 event-related potential (ERP) component using a publicly available novel set of sentences with semantically congruent or incongruent endings.*  
Neuroscience, 501, 143–158.

Data were obtained from the Dryad Digital Repository (BIDS-formatted EEG).

---

## Dataset & Experimental Design (Brief)

- 128-channel BioSemi EEG (512 Hz sampling rate)
- Auditory sentence comprehension task
- Congruent vs incongruent sentence endings
- Additional factors:
  - Semantic vs semantic+syntactic violations
  - Experimental quarter (1–4)
  - Order effects

The critical time-locking event was the onset of the final word in each sentence.

---

## Preprocessing Strategy (High-Level)

Key preprocessing steps included:

- Removal of non-EEG (EXG) channels
- Band-pass filtering (0.1–45 Hz; Butterworth IIR)
- Identification of bad channels using provided metadata
- Spherical interpolation of rejected channels
- Common average re-referencing
- Reconstruction of event codes from stimulus timing files
- Epoching (−200 to 1000 ms) and baseline correction
- Artifact rejection using a ±250 µV threshold

Some preprocessing choices differed slightly from the original study due to
software constraints and documentation gaps.

---

## Analysis Focus

Primary analyses focused on:

- Replication of the classic N400 effect (congruent vs incongruent)
- ERP waveform morphology at midline electrodes (Cz, Pz)
- Topographical patterns of semantic incongruity
- Exploratory analyses of later components (P600/LPC)

Statistical analyses included paired t-tests and repeated-measures ANOVA
at standard a priori time windows.

---

## Outcome & Reflection

- The core N400 incongruity effect was successfully replicated
- ERP morphology and scalp distributions were consistent with prior literature
- The most challenging aspects were:
  - Understanding BIDS data organization
  - Reconstructing event codes
  - ERP preprocessing decisions

This project was primarily a learning experience that connected theoretical
ERP concepts to real, complex EEG data and highlighted the value of open datasets
and collaborative research environments like BrainHack.

## Contributors

This project was developed collaboratively as part of an ERP course and BrainHack.

- Ivo Niethammer
- 李欣潔
- 徐執允
