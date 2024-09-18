MIDIFAM User Manual
===================


# MIDI Channel Preferences

Press the "Learn" button to set your MIDI channel preferences. There are three selections to make and they will be presented in the following order:

1. CV *A*
2. CV *B*
3. DFAM *Note On* mode
    - When the toggle switch is set to *Note On*, DFAM sequencer steps will be triggered by notes received on this MIDI channel

The LEDs will light to indicate which selection is currently active.

To make a MIDI channel selection, **send any Note On message on your chosen MIDI channel**. The module will detect the message and save the MIDI channel on which it was received.

When the selection has been made, the module will automatically advance to the next output and will await a new selection (i.e. any MIDI Note On message on any channel). **To skip to the next selection without changing channel preference, press the "Learn" button again.**

When you have updated (or skipped) all three channel preferences, the module will *store all current configuration* to persistent storage so that your preferences are saved even after power cycling. In addition to saving the MIDI channel selections, **all other settings will also be saved** (e.g. portamento, vibrato, polyphony, and any other configuration made using MIDI CC messages).

By default:
- CV output A receives on MIDI channel #1
- CV output B receives on MIDI channel #2
- DFAM *Note On* mode receives on MIDI channel #10


# Channel-specific CC messages

These will only apply when they are sent on the MIDI channel to which the CV output is assigned.

**Portamento**

|CC | Function           | Values                         | Notes |
|---|--------------------|--------------------------------|-------|
|65  |   Enable or disable portamento | On/Off | |
|18	|   Time (desc.) | 0 to 2 sec | Duration of slides for descending notes |
|19	|   Time (asc.) | 0 to 2 sec |  Duration of slides for ascending notes |
|5	|   Time (master) | 0 to 2 sec | Master duration  |


**Gate/Trig Behavior**

|CC | Function           | Values                         | Notes |
|---|--------------------|--------------------------------|--------- |
|16 | Trigger duration   | 1ms to about 50ms              | |
|80 | Retrigger behavior | Off, Highest, Lowest, Latest   | What note to re-trigger if any notes are still held when a Note Off message is received |
|81 | Gate/Trig mode     | Off, Trigger, Gate             | "Trigger" means a short pulse for every MIDI Note On. "Gate" means the output is high as long as a note is held. |


**Vibrato**

|CC | Function       | Values                         | Notes|
|---|----------------|--------------------------------|-------------|
|76 | Rate           | 5 sec to 200 ms period    |  |
|77 | Depth          | 0 to 1 semitone           | What note to re-trigger if any notes are still held when a Note Off message is received|
|78 | Delay          | 0 to 3 seconds            | How long to wait before beginning the vibrato|

**Pitch Bend**


|CC | Function       | Values                         | Notes|
|---|----------------|--------------------------------|-------------|
|17 | Pitch bend range           | 0 to 12 semitones   |  | 


## Global CC Messages


|CC | Function       | Values                         | Notes|
|---|----------------|--------------------------------|-------------|
|83 | Clock divider  | 1, 2, 3, 4, 6, 8, 12    | Default=4. When the toggle switch is set to "Clock", change the speed of the DFAM sequencer |
|126 | Mono Mode on  |                         | Each CV output is independent and operates as a single monophonic output |
|127 | Poly Mode on  |                         | Both CV outputs are combined for duophony |

