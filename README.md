
# JND Frequency Discrimination Threshold Experiment

This repository contains a browser-based psychoacoustic experiment designed to measure the **Just Noticeable Difference (JND)** for frequency around a 1000 Hz reference tone. The experiment uses a **2AFC adaptive staircase** to estimate frequency discrimination thresholds across **three independent blocks**.

---

## 1. Overview

Participants hear **two tones** on each trial—one fixed at **1000 Hz**, the other slightly higher at **1000 Hz + Δf**.
They must decide which tone was higher:

* **Press K** → 1st tone was higher
* **Press L** → 2nd tone was higher

Δf shrinks or grows based on performance, allowing the program to converge on the perceptual threshold.

The experiment runs entirely in the browser using:

* HTML + TailwindCSS
* JavaScript
* **Web Audio API** for tone generation
* Built-in results export via email

---

## 2. Experiment Structure

### Blocks

* Total blocks: **3**
* Each block produces a separate JND estimate
* Final threshold is the **average** of the three block JNDs

### Trial Flow

1. 250 ms tone
2. 500 ms silence
3. 250 ms tone
4. Participant response
5. 1-second inter-trial interval

### Tone Synthesis

* Sample rate: **44,100 Hz**
* Duration: **250 ms**
* Ramp in/out: **10 ms cosine-squared**
* Amplitude normalized to avoid clipping

---

## 3. Staircase Method

### Rule

**2-down / 1-up adaptive staircase**
→ converges near **70.7% correct**, a standard psychophysical threshold.

### Parameters

* Initial Δf = **200 Hz**
* Primary step factor = **2.0**
* Secondary step factor = **1.414** (after reversal switch point)
* Reversal switch point = **4**
* Max reversals per block = **8**

### Reversal Handling

A reversal occurs when Δf changes direction (increasing → decreasing, or vice versa).

JND for each block is computed from the **geometric mean** of the final reversals.

---

## 4. Data Recorded

For each block the script stores:

* Δf on every trial
* All reversal values
* Final JND for that block

After all blocks:

* The three JNDs are averaged
* Final results are displayed visually
* A button allows export via **mailto:** including:

  * Block JNDs
  * Final mean JND
  * Full Δf histories (CSV-formatted)

---

## 5. How to Run the Experiment

### Step 1 — Open the HTML file

Simply open **index.html** in any modern browser (Chrome recommended).

### Step 2 — Start

Click **Start Experiment**.
This enables the audio context (required for browser audio playback).

### Step 3 — Complete the Blocks

Follow on-screen instructions on the participant screen overlay.
You will complete three blocks, each ending after 8 reversals.

### Step 4 — View Results

At the end you will see:

* JND per block
* Final averaged JND

### Step 5 — Export Results

Click **Share Results via Email** to send the raw data to the experimenter.

---

## 6. Technical Notes

### Web Audio

The script manually generates sinusoidal tones using typed buffers.
Ramps are applied to avoid onset/offset clicking.

### Dual-Screen System

The UI contains two synchronized views:

* **Participant Screen:** full-screen overlay (black) showing only task-essential content
* **Experimenter Screen:** control panel + log

Both remain active throughout the session.

### Compatibility

* Works in Chrome, Edge, and Firefox (with Web Audio enabled)
* Not recommended on mobile devices
* Requires user interaction before first tone (browser security)

---

## 7. Files

```
index.html    # full experiment (UI, audio, staircase logic)
```

The experiment is fully self-contained in this single file.

---

## 8. Customization

You may edit:

### Frequency parameters

* Center frequency
* Δf start value
* Tone durations
* ISI / ITI

### Staircase parameters

* Step factors
* Reversal count
* Down/up rule

### UI

* Instructions
* Color scheme
* Participant/experimenter screen text

---

## 9. License

You are free to modify and use this experiment for research, coursework, or teaching.

---

If you want, I can also generate:

* a **GitHub-optimized formatted README**
* a **PDF user manual**
* a **Methods section** suitable for publications
* a **flowchart or diagram** of the experiment logic
