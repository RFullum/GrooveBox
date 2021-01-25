# GrooveBox
Pure Data Synth &amp; Sequencer sync'd via Ableton Link

Pure Data patch designed to fit on my Raspberry Pi 3a+ w/7" Touchscreen.

Videos of patch in action (with previous layout):

https://youtu.be/Qm14gKKZAeA

https://youtu.be/-91xlZS8tXk

https://youtu.be/bX5pd7wVPfk

Main Patch:
  - rf.GrooveBox.pd (Open this one to run patch)

Sub patches:
  - rf.ADSR.pd
  - rf.grooveBoxInterface.pd
  - rf.grooveBoxSynth.pd
  - rf.oscillatorBlend.pd

Externals:
  - abl_link~/
  - cyclone/
  - tof/

The DSP toggle on the top right turns DSP on/off. (Play/Stop)

Link toggle links to Ableton Link sessions over network WiFi. Tempo control works in both directions.
rsltn (resolution), beat, and quntm (quantum) are Link parameters. Can be altered, but mainly used to show beat/bars.
(See abl_link~ help for more info).
Set BPM slides BPM of Link session up or down.

Reset Zero: starts sequence at beginning. For example: Hit it on the downbeat to ensure PD and Live are both on the 1 like a DJ sync'ing beats.

current tempo: BPM display (no control)
1/4, 1/8, 1/16: Beat division of grid
slice: current slice of 16 beats (0-15)

Sequencer grid:
  - 16 notes (vertically) x 16 steps (horizontally)
  - Toggle notes on/off
  - clear: clears all notes to off
  - pitch: transpose notes up or down. Displays Midi note number of lowest note
  - Color pattern repeats colors at the octave. (Bright Red is Root & Octave)

ADSR:
  - A: Attack time
  - D: Decay (Time & Level)
  - S: Sustain time
  - R: Release time
  - Breakouts box shows current state of ADSR sliders. Can be manually modified, but ADSR sliders will reset
  - Curves are non-linear for more accuracy at lower values

out gain: output gain 0 - 1.2 (1.0f = unity)

osc blend: blends amounts of three waves, sine, spike (highpassed square), and saw.
            Sine  Spike Saw
  - Top   : 0%    0%    100%
  - Middle: 0%    100%  0%
  - Bottom: 100%  0%    0%
  - Curves are non-linear for better blending.

Filter:
  - bandpass/lowpass selector toggle
  -Filter and Resonance sliders non-linear to give better feel and better low-frequency accuracy

Still plan on updating:
  - versions with different synth sub-patch for different sounds
  - some sort of reverb/fx (My RasPi 3a+ w/HiFiBerry ADC + DAC Pro didn't like running the patch with Freeverb running. It got very upset with me.)
