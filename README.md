🔬 Frequency Just Noticeable Difference (JND) Web Experiment

This is a single-file, web-based psychoacoustic experiment designed to measure the Just Noticeable Difference (JND) for frequency, primarily aimed at $\mathbf{1000 \text{ Hz}}$.

The application runs entirely in a modern web browser, using the Web Audio API for accurate stimulus generation and precise timing.

Technical Specifications

The experiment strictly adheres to the following adaptive staircase and stimulus parameters:

Parameter

Value

Description

Task

2I-2AFC

2-Interval, 2-Alternative Forced Choice (Higher Pitch)

Algorithm

Two-Down, One-Up

Targets the $\approx 70.7\%$ correct threshold.

Center Frequency

$1000 \text{ Hz}$

The standard frequency for comparison.

Blocks

3

The total number of staircase runs per participant.

Tones

$250 \text{ ms}$ duration

Stimulus length.

Ramps

$10 \text{ ms}$ onset/offset

Cosine ramps to eliminate clicks.

ITI / ISI

$1000 \text{ ms} / 500 \text{ ms}$

Inter-Trial Interval / Inter-Stimulus Interval.

Starting $\Delta F$

$200 \text{ Hz}$

Initial frequency difference.

Step Factor

Variable: $2.0 \rightarrow 1.414$

Coarse factor ($\times 2.0$) for first 4 reversals, then fine factor ($\times 1.414$) for final 4 reversals.

Stopping Rule

8 Reversals

The staircase terminates after 8 reversals.

Usage and Data Output

Participants interact via keyboard input ('K' and 'L'). Upon completion, the experiment calculates the final JND (geometric mean of the final 4 reversals) and provides a Share Results via Email button. This function packages the final JND and the complete, trial-by-trial raw $\Delta F$ history into a comma-separated format for easy analysis by the experimenter.
