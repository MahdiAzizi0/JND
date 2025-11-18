# JND Frequency Discrimination Experiment

This is an interactive, browser-based test that measures how small a pitch difference you can reliably hear around **1000 Hz**. You’ll listen to pairs of tones, decide which one was higher, and the program will automatically adjust difficulty to find your **Just Noticeable Difference (JND)**.

---

## How the Experiment Works

* Each trial plays **two tones**: one at 1000 Hz, the other slightly higher.
* You answer using your keyboard:

  * **K** → first tone was higher
  * **L** → second tone was higher
* The difference between the tones (**Δf**) gets smaller when you’re right and bigger when you’re wrong.
* You complete **3 blocks**, each giving one JND estimate.

After the final block, the program shows:

* Your JND for every block
* Your overall average
* A button to **email the results** (includes raw Δf data)

---

## Running the Experiment

1. Open the **HTML file** in any modern browser (Chrome recommended).
2. Click **Start Experiment** (this activates audio).
3. Follow the on-screen instructions.
4. At the end, view or share your results.

Use **headphones** and try to be in a quiet room for best accuracy.

---

## Technical Notes

* Tones are generated with the **Web Audio API**.
* The task uses a standard **2-down/1-up staircase** to estimate threshold.
* The JND for each block is computed from the final reversal values.
* Everything (UI, logic, audio, export) is contained in a single HTML file.

