# stroop-cognitive-fatigue-paradigm

a 30 minute colour-word Stroop Task, with Borg CR100 cognitive fatigue probes every 10 minutes, built in PsychoPy.

## What it does

- practice block (12 trials) followed by a 30 minute main task
- congruent and incongruent colour-word trials (red, green, blue)
- Borg CR100 mental fatigue probes at baseline, 10 min, 20 min, and task end (NOTE: the CR100 scale was originally designed for perceived physical exertion; here, participants apply the same ratio-scaling logic to rate subjective mental fatigue)
- paused time during probes is tracked and excluded from elapsed task time
- runs locally on PsychoPy or online via Pavlovia (JS auto-generated)

## Task structure

1. instructions
2. Borg CR100 scale explanation + baseline fatigue rating
3. practice block (12 randomised trials)
4. main task (30 min, ~300-400 trials depending on response speed)
5. fatigue probes at 10 min intervals
6. outro

## Custom code components

this experiment uses several custom Python code components beyond PsychoPy standard builder interface:

- **timer_code** , manages a 30 minute task clock, tracks elapsed time excluding paused periods, and triggers the fatigue probes at 10 minute intervals
- **gate_code** , conditionally displays fatigue probes only when a probe is due, prevents confirmation without a slider response
- **probe_code** , logs Borg CR100 ratings, response times, and probe labels (inc. baseline, task_10, task_20, task_end)
- **pause_code** , tracks time spent on probe screens and subtracts it from the task elapsed time so the 30 minute window reflects actual task engagement


## Note on Borg CR100 scale images

the Borg CR100 scale images are not included in this repo due to copyright. To run the experiment, you will need to obtain the scale from the original source:

[BorgPerception](https://borgperception.se/obtain-a-license-for-research-and-education/)

Borg, G., & Borg, E. (2001). A new generation of scaling
methods: Level-anchored ratio scaling. Psychologica, 28, 15–45.

The Borg centiMax scale® (CR100) © Gunnar Borg & Elisabet Borg,
2001, 2002, Elisabet Borg, 2007. The scale and full instruction
can be obtained through BorgPerception [](www.borgperception.se)

place the instruction and scale images in the project directory and update the file paths in the .psyexp file.

## Requirements

- [PsychoPy](https://psychopy.org/index.html) 2024.1 or later
- 'conditions.xlsx' (included)
- Borg CR100 scale images (see above)

## Running the task

1. open 'stroop_task_updated.psyexp' in PsychoPy (builder view)
2. ensure 'conditions.xlsx' and the Borg CR100 scale images are in the same directory
3. click run

## Author

Jess Inglis, BSc, Edinburgh Napier University

Developed in July 2026 for a study on cognitive effort and recovery at Edinburgh Napier University
