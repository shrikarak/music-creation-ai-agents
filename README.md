# Music Creation using a Multi-Agent AI System

Copyright (c) 2026 Shrikara Kaudambady. All rights reserved.

## 1. Introduction

This project brings the concept of a collaborative band into the world of AI through a Jupyter Notebook that simulates a group of "AI Musician Agents." Instead of a single monolithic model generating music, this solution uses a multi-agent system where each agent has a distinct role—drummer, bassist, and melody player—and follows its own set of rules to contribute to a collective composition.

The result is a unique piece of symbolic music generated from the ground up, guided by musical theory and probabilistic creativity. The final output is a MIDI file, which can be played in any Digital Audio Workstation (DAW) or online sequencer.

## 2. The Solution Explained: A Band of AI Agents

The core of this project is a multi-agent system built on the principle of **algorithmic composition**. Each agent operates with a degree of autonomy, but their collective work is coordinated by a central "Orchestrator."

### 2.1 The Agents and Their Roles

1.  **The Orchestrator Agent:** This agent acts as the bandleader. It doesn't play an instrument but sets the global parameters for the song:
    *   **Key and Scale:** The musical framework for the composition (e.g., C Major).
    *   **Chord Progression:** The harmonic structure of the song (e.g., I-V-vi-IV).
    *   **Tempo (BPM):** The speed of the song.
    *   It directs the other agents by telling them which chord to play for each measure.

2.  **The `DrummerAgent`:** This agent's goal is to provide a steady, rhythmic foundation. Its behavior is rule-based:
    *   It lays down a kick drum on beats 1 and 3.
    *   It places a snare drum on beats 2 and 4.
    *   It adds hi-hats on every eighth note to maintain the groove.

3.  **The `BassistAgent`:** This agent provides the harmonic backbone of the music. Its rules are tied to the chord progression:
    *   It primarily plays the root note of the current chord being dictated by the Orchestrator.
    *   It adds simple arpeggios or passing notes from the song's scale to create a fluid bassline.

4.  **The `MelodyAgent` (Violin):** This agent is the most creative and uses a probabilistic approach to generate the main tune:
    *   It is constrained to play notes within the song's key and scale.
    *   It uses a **Markov chain** or a **weighted random walk** to decide the next note. This means the choice of the next note is influenced by the current note, creating a more coherent and "human-like" melody than pure randomness would allow.

### 2.2 Symbolic Music Output (MIDI)

It is important to note that this system generates **symbolic music**, not audio. The output is a `.mid` file, which is a set of digital instructions (like sheet music for a computer) that specify which notes to play, when to play them, and for how long. This file can be imported into any music software, where you can assign different virtual instruments to each part to hear the final composition.

## 3. How to Use the Notebook

### 3.1. Prerequisites

This project requires the `mido` library to create MIDI files. You can install it via pip:

```bash
pip install mido numpy
```

### 3.2. Running the Notebook

1.  Clone this repository:
    ```bash
    git clone https://github.com/shrikarak/music-creation-ai-agents.git
    cd music-creation-ai-agents
    ```
2.  Start the Jupyter server:
    ```bash
    jupyter notebook
    ```
3.  Open `generative_music_agents.ipynb` and run all the cells.

### 3.3. Listening to the Music

After running the notebook, a file named `ai_composition.mid` will be created in the same directory. To listen to your AI-generated song:
*   **Easy Method:** Drag and drop the `ai_composition.mid` file into an online sequencer like [onlinesequencer.net](https://onlinesequencer.net/).
*   **Advanced Method:** Import the MIDI file into any Digital Audio Workstation (DAW) like GarageBand, FL Studio, Ableton Live, or Logic Pro. This will allow you to assign high-quality virtual instruments to each track.

## 4. Deployment and Customization

This notebook is a fun and powerful template for exploring algorithmic composition.

1.  **Change the Song Structure:** Modify the `KEY`, `SCALE`, `CHORD_PROGRESSION`, and `BPM` variables in the notebook to create an entirely new song.
2.  **Modify Agent Behavior:**
    *   Change the rules in the `DrummerAgent` to create different beats (e.g., a funk or jazz rhythm).
    *   Adjust the logic in the `BassistAgent` to make its basslines more or less complex.
    *   Tweak the probabilities in the `MelodyAgent` to change its melodic style.
3.  **Add New Agents:** Create a new class for a `PianoAgent` that plays chords or a `FluteAgent` that plays a counter-melody. Add the new agent to the Orchestrator's list of musicians to include it in the composition.
