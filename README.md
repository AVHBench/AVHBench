# AVHBench
This repository contains dataset for the NeurIPS 2024 Submission, \
[AVHBench: A Cross-Modal Hallucination Evluation for Audio-Visual Large Language Models].

<img width="1503" alt="AVHBench_teaser" src="https://github.com/AVHBench/AVHBench/assets/171882807/82cdc40a-1c1b-4d9d-80f1-a11e37a029b5">

## Download the AVHBench Dataset
At this time, we provide a subset of AVHBench, which includes both real and synthetic (swapped) video samples.

1. Download AVHBench dataset v.0 in [here](https://drive.google.com/file/d/1bLHjdlk0G51RfIztXPNmWkqd3nvy7KLT/view?usp=sharing)
2. Unzip the dataset.

    ```
    AVHBench_v0
        |
        |
        └── json
        |     ├── 00006.json
        |     ├── 00159.json
        |     └── ...   
        |           
        └── video
             ├── 00006.mp4
             ├── 00006_swap.mp4
             └── 00159.mp4
             └── 00159_swap.mp4
             └── ...
    ```
3. Details of each file in the dataset
   - **{video_id}.json**: Question-and-Answer pairs for the video, which contain the metadata of: (1) video id, (2) type of hallucination task, (3) input text prompt, and (4) ground-truth label. We provide an axample of json file below:
     
       ```
      [
          {
            "video_id": "00191",
            "task": "Video-driven Audio Hallucination",
            "text": "Is the sleeping man making sound in the audio?",
            "label": "Yes"
          },
          {
            "video_id": "00191",
            "task": "Video-driven Audio Hallucination",
            "text": "Is the couch making sound in the audio?",
            "label": "No"
          },
          {
            "video_id": "00191",
            "task": "Audio-driven Video Hallucination",
            "text": "Is the sleeping man visible in the video?",
            "label": "Yes"
          },
          {
            "video_id": "00191",
            "task": "Audio-driven Video Hallucination",
            "text": "Is the person walking visible in the video?",
            "label": "No"
          },
          {
            "video_id": "00191",
            "task": "AV Matching",
            "text": "Are the contexts of audio and visual content matching?",
            "label": "Yes"
          },
          {
            "video_id": "00191",
            "task": "AV Captioning",
            "text": "Describe what you see and hear in a single sentence.",
            "label": "A young man with no shirt on is laying in bed, with footsteps walking on a hard surface followed by a person snoring."
          }
      ]
       ```
   - **{video_id}.mp4**: a real video sample sourced from VALOR and Audiocaps.
   - **{video_id}_swap.mp4**: a synthetic video sample generated by swapping the audio in the real video with another audio.


## Acknowledgement
We are grateful for the following awesome projects, our AVHBench arising from:
- [GPT4](https://arxiv.org/abs/2303.08774): Language Models are Few-Shot Learners
- [Recognize Anything Model](https://github.com/xinyu1205/recognize-anything): Visual Tagging Models for Dataset Construction Pipeline
- [VALOR](https://github.com/TXH-mercury/VALOR): VALOR: Vision-Audio-Language Omni-Perception Pretraining Model and Dataset
- [AudioCaps](https://audiocaps.github.io/): AudioCaps: Generating Captions for Audios in the Wild

