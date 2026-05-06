# unsupervised-music-generation
Unsupervised Music Generation

Project Overview

This project explores multiple deep learning approaches for symbolic music generation using MIDI data. It compares traditional baselines with modern neural architectures and further improves generation quality using reinforcement learning with human-inspired rewards.

The pipeline starts from raw MIDI preprocessing and ends with generated music samples evaluated using metrics.

Models Implemented
1. Baseline Models
Random Generator
Markov Chain Model

These serve as simple references for comparison.

2. LSTM Autoencoder (AE)
Learns compressed representation of piano roll sequences
Reconstructs input sequences
Limited diversity but stable structure


3. Variational Autoencoder (VAE)
Learns latent distribution of music
Enables sampling + interpolation
Produces more diverse outputs than AE

4. Transformer Model
Uses self-attention for sequence modeling
Captures long-range dependencies
Generates higher-quality structured music

5. RLHF (Reinforcement Learning with Human Feedback)
Fine-tunes Transformer model
Uses reward based on:
Rhythm diversity
Repetition control
Improves musical quality and coherence

Dataset
Dataset used: MAESTRO v3.0.0 MIDI
Preprocessing steps:
MIDI → Piano Roll (binary)
Window slicing (100 timesteps)
Filtering low-activity samples

Workflow
1. Data Preprocessing
Extract MIDI files
Convert to piano roll representation
Create training dataset

Model Training
Model	Input Shape	Output
AE	(100, 128)	Reconstruction
VAE	(100, 128)	Generated samples
Transformer	(30, 128)	Next-step prediction

Music Generation
Convert predicted piano rolls → MIDI
Save .mid files for listening

# Evaluation Metrics

Objective Metrics
Pitch Distribution Distance
Rhythm Diversity
Repetition Ratio

Subjective Metric
Simulated Human Score (1–5)

Key Insights
AE reconstructs well but lacks creativity
VAE introduces diversity via latent space
Transformer significantly improves structure
RLHF further refines musical quality using reward feedback

Limitations
Binary piano roll loses velocity dynamics
Small dataset reduces generalization

Future Work
Use larger dataset (full MAESTRO)
Add velocity + timing modeling
Replace simulated reward with real human feedback
Try diffusion models for music generation

#######How to Run:###########
1) Open the notebook
2) Run all cells step by step

Notes:
Project developed using Google Colab


Run the notebook directly in Google Colab for full execution.
