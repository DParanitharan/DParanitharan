# GLINT — Dark-Vessel Detection & AIS Correlation

**Singapore Defence Tech Hackathon** · *Ship Detection & AIS Correlation Lead* · Jun 2026 – Present

## Problem
Some vessels switch off their AIS transponders to move undetected ("dark vessels"). GLINT is a 3-person maritime-surveillance system that flags such ships by comparing what radar *sees* against what transponders *report* over the Singapore Strait.

## My Role
I owned the **vessel detection** and **AIS correlation** components — the perception-to-evidence half of the pipeline — integrating my teammates' world-model outputs and passing validated evidence records downstream to the analyst console and an LLM agent.

## Approach

### Detection
- **ResNet-18 + FPN** vessel detector trained with **focal loss** to handle the extreme foreground/background imbalance typical of SAR.
- **Water-only median/MAD normalisation** so sea-clutter statistics don't get skewed by land and bright targets.
- Reached **0.79 recall on 1,150 labelled vessels**.
- Paired the learned detector with a classical **CA-CFAR** baseline to maximise combined precision.

### Correlation
- Matched radar detections to AIS reports using **Hungarian assignment**, with **dead-reckoning** and **speed-gating** to account for the time offset between a detection and the nearest transponder ping.
- Redesigned the matching logic after a **US Navy operator review**, extending the tolerated AIS delay before raising a false dark-vessel alert.

## Stack
Python · PyTorch · Sentinel-1 SAR · CA-CFAR · Hungarian algorithm

## Outcome
An end-to-end detection → correlation → evidence pipeline that surfaces likely dark vessels with reviewer-tuned false-alarm behaviour.
