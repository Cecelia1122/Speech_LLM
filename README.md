# A Comparative Study of Speech-to-Speech Translation Architectures

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](YOUR_SHAREABLE_COLAB_LINK_HERE)

**This project is an interactive Google Colab notebook. Please click the badge above to open and run the live environment.**

---

## Overview

This repository contains the code and documentation for a comparative study of three distinct architectures for speech-to-speech translation. This project was developed to demonstrate a practical, hands-on understanding of the modern Speech AI ecosystem, moving from classical cascaded systems to state-of-the-art, end-to-end models.

The entire project is self-contained within the Colab notebook, which handles all environment setup, data processing, model execution, and evaluation.

## The Three Pipelines Under Comparison

This study implements and analyzes the following architectural patterns:

### Approach A: The "Pragmatic Baseline"
*   **Flow:** `Speech → Whisper (task=translate) → English Text → English TTS (SpeechT5)`
*   **Purpose:** To establish a fast, efficient baseline for English-only translation by leveraging the integrated translation capabilities of the Whisper model.
*   **Trade-offs:** High speed and simplicity, but limited to English as the target language.

### Approach B: The "High-Quality Modular" Pipeline
*   **Flow:** `Speech → Whisper (ASR) → Machine Translation (M2M100) → Multilingual TTS`
*   **Purpose:** To build a best-in-class, flexible, and truly multilingual system by chaining together specialized, state-of-the-art models for each distinct sub-task.
*   **Trade-offs:** Achieves the highest translation quality and versatility, at the cost of increased complexity and potential for error propagation.

### Approach C: The "Next-Generation End-to-End" Pipeline
*   **Flow:** `Speech → SeamlessM4T (Direct S2ST) → Audio`
*   **Purpose:** To explore the cutting-edge, end-to-end paradigm that translates directly from audio to audio, bypassing the intermediate text representation.
*   **Trade-offs:** Potential to better preserve the prosody and paralinguistic cues of the original speech, but with less modularity than a cascaded system.

---

## Features & Methodology

The notebook is structured into a clear, multi-part pipeline:

*   **Part 1 - Environment Setup:** Handles all package installations and configuration. Includes optional integration with Google Drive to persist models and data between sessions.
*   **Part 2 - Data Intake & Preprocessing:** Automatically scans for input audio files, normalizes them, and resamples to 16 kHz mono to meet model requirements.
*   **Parts 3, 4, 5 - Pipeline Execution:** Contains the implementation for each of the three approaches described above.
*   **Part 6 - Evaluation & Comparison:**
    *   **Objective Metrics:** Calculates and compares the pipelines on end-to-end latency, Word Error Rate (WER), and BLEU scores for 
