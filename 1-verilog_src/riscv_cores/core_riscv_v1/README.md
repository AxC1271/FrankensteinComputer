# RISC-V v3: 2-way In-order Superscalar Processor

## Overview

The first version of the core used for the SCUFF-DOS features a 2-way superscalar in-order core with dual-path forwarding and branch prediction. This README gives more into depth about the microarchitecture, the implemnetations, and motivation for designing this core. To see more details on implementation/explanation on specific design choices, check out the RISC-V v3 repository in my GitHub bio.

---

## Frontend

### Instruction Fetch

This core is a 2-wide machine and fetches two instructions at a time. The program counter increments by `0x8` on normal operations unless redirected by a branch/jump instruction. There is no dedicated instruction queue module; the CPU simply fetches two instructions and inserts them into the pipeline directly from its input ports.

### Branch Prediction

For this specific design, I chose to incorporate a bimodal saturating counter as its primary branch predictor due to its simplicity. In future implementations, I could consider more sophisticated branch predictor schemes like TAGE, perceptron-based, or tournament predictors. Since I'm aiming to be oonservative on hardware resources, I felt that the bimodal predictor is a perfectly fine choice. 

### Instrucion Decode

Nothing much has changed from the normal 5-stage scalar pipeline from this. Both instructions are

---

## Backend

### Execution

### Memory/Writeback

---

## Testbenches/Verification

---

