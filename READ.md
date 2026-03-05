# RA-QA: Respiratory Audio Question Answering Benchmark

<p align="center">
  <img src="chatbot.png" alt="RA-QA Overview" width="860"/>
</p>

<p align="center">
  <b>RA-QA is a large-scale benchmark for Respiratory Audio Question Answering</b><br/>
</p>

<p align="center">
  <!-- Replace with your links -->
  <!-- <a href="https://arxiv.org/abs/XXXX.XXXXX">Paper</a> • -->
  <!-- <a href="https://doi.org/10.5281/zenodo.XXXXXXXX">Zenodo</a> • -->
  <!-- <a href="#citation">Citation</a> -->
</p>

---

## What is RA-QA?

**RA-QA (Respiratory-Audio Question Answering)** is a benchmarking framework and dataset release that turns heterogeneous public respiratory-audio datasets into a **unified multimodal QA collection**.

RA-QA provides:
- a **standardized data generation pipeline** ,
- **format-diverse QA files** (open-ended / multiple-choice / single-verify),
- a **unified evaluation protocol** for both **discriminative** (categorical) and **regression** (continuous) targets.

This benchmark is designed to stress-test models under **real-world heterogeneity**: different datasets, recording conditions/devices, audio modalities (e.g., cough/breath/speech/auscultation), and question intents.

---

## What’s in this repository?

This repo is organized around two deliverables:

1) **Standardized metadata**  
Per-dataset harmonized tables/JSON exposing canonical attributes and provenance.

2) **QA files**  
Generated QA pairs in multiple formats (OE/MC/SV), linked to recordings/subjects.

        test.jsonl
