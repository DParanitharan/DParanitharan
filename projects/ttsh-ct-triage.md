# Tan Tock Seng Hospital — CT Triage Pipeline

*Computer Vision Intern (Full-time)* · May 2026 – Aug 2026

## Context
CT pulmonary angiograms need to be read quickly when a patient may have a pulmonary embolism (PE) or right-heart strain. The goal: automatically **rank the radiology worklist into urgency tiers** so the sickest patients surface first.

## What I Did
- **Rebuilt an ~11.5k-line CT triage pipeline** that screens CT pulmonary angiograms for pulmonary embolism and right-heart strain, ranking the worklist into **4 urgency tiers**.
- **Redesigned four always-on models into a gated cascade**: an **SE-ResNeXt-101 + Bi-GRU** detector escalates only *uncertain* scans to the heavier **MedSigLIP** and **MedGemma** models — cutting compute while preserving sensitivity.
- **Replaced a trained 3D heart-strain model with a zero-training right/left ventricle (RV/LV) ratio**, and implemented **lung-mask cropping** that roughly **doubled effective image resolution**.
- Authored an **AI learning-pathway framework for NHG Health** covering **11 staff roles across 4 tiers**, with a 0–4 proficiency scale and pre/post self-assessment.

## Stack
Python · PyTorch · SE-ResNeXt-101 · Bi-GRU · MedSigLIP · MedGemma · TotalSegmentator · DICOM/CT

## Impact
A leaner, faster triage pipeline that spends heavy compute only where needed, with a measurable resolution gain from smarter preprocessing.
