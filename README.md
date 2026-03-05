# RA-QA: A Benchmarking System for Respiratory Audio Question Answering Under Real-World Heterogeneity

<p align="center">
  <img src="chatbot.png" alt="RA-QA Overview" width="860"/>
</p>

<p align="center">
  <b>RA-QA is a large-scale benchmark for Respiratory Audio Question Answering which covers real-world heterogeneity across modalities, devices, and question types</b><br/>
</p>


**Dataset availability.** This repository currently provides a **preview release** of RA-QA.  
> The **full RA-QA collection** (standardized metadata, complete QA files, and the generation pipeline) will be made **publicly available upon acceptance of the RA-QA paper**.
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
Generated QA pairs in multiple formats (OE/MC/SV), linked to recordings/subjects, structured in a JSON format style.

### QA JSON format (example)

Each split is stored as a single JSON file containing a **list of QA records**.  
Below is an example entry for a **single-verify** question:

```json
[
  {
    "id": 0,
    "question_id": 1,
    "version": 1,
    "patient_id": "01GtHP1FUbXKdWEUwApFdusuO773",
    "split": "train",
    "question_type": "single-verify",
    "question": "Does the patient suffer from asthma?",
    "answers_list": [
      "Yes, the patient suffers from asthma.",
      "Yes, the patient suffers from asthma.",
    ],
    "audio_filename_list": [
      "20220224_01GtHP1FUbXKdWEUwApFdusuO773_breathing-shallow.wav",
      "20220224_01GtHP1FUbXKdWEUwApFdusuO773_cough-heavy.wav",
    ],
    "attribute": "asthma"
  }
]
```

### QA JSON fields

Each QA file is a JSON **array of records**, where each record has the following fields:

- `id` *(int)*: Unique record index within the file.
- `question_id` *(int)*: Identifier of the underlying question template / generation rule.
- `version` *(int)*: Version tag for the generation pipeline/templates used to create this record.
- `patient_id` *(str)*: Patient identifier used to group multiple recordings belonging to the same subject.
- `split` *(str)*: Dataset split for this record. One of `{train, val, test}`.
- `question_type` *(str)*: Question format. One of `{open-ended, multiple-choice, single-verify}`.
- `question` *(str)*: Natural-language question text.
- `answers_list` *(list[str])*: List of acceptable natural-language reference answers (multiple references per question).
- `audio_filename_list` *(list[str])*: List of audio filenames associated with the `patient_id` (e.g., cough/breath/speech recordings).
- `attribute` *(str)*: Canonical target attribute queried by the question (e.g., `age`, `asthma`, `device`, `severity`).
