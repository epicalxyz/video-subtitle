## Automatic subtitles your videos using your GPU

This repository uses `torch`, `ffmpeg` and [OpenAI's Whisper](https://openai.com/blog/whisper) to automatically generate and overlay subtitles in videos

Currently tested with Nvidia 3060 12GB

- Using CPU: 485.99frames/s
- Using GPU: 2605.99frames/s

## Installation

### Use python virtual environments
Remember to use python virtual environment to isolate your project dependencies

```bash
# You can change the name of "venv" to whatever you want
python3 -m venv venv

# Activation of Virtual Environment
.venv/bin/activate

# Deactivation
deactivate
```

### Install the required packages

```bash
pip install -r requirements.txt
```
### Usage
```bash
python cli.py --video "name_of_the_video.mp4"
```

## Available models and languages
Source: https://github.com/openai/whisper

There are six model sizes, four with English-only versions, offering speed and accuracy tradeoffs.
Below are the names of the available models and their approximate memory requirements and inference speed relative to the large model.
The relative speeds below are measured by transcribing English speech on a A100, and the real-world speed may vary significantly depending on many factors including the language, the speaking speed, and the available hardware.

|  Size  | Parameters | English-only model | Multilingual model | Required VRAM | Relative speed |
|:------:|:----------:|:------------------:|:------------------:|:-------------:|:--------------:|
|  tiny  |    39 M    |     `tiny.en`      |       `tiny`       |     ~1 GB     |      ~10x      |
|  base  |    74 M    |     `base.en`      |       `base`       |     ~1 GB     |      ~7x       |
| small  |   244 M    |     `small.en`     |      `small`       |     ~2 GB     |      ~4x       |
| medium |   769 M    |    `medium.en`     |      `medium`      |     ~5 GB     |      ~2x       |
| large  |   1550 M   |        N/A         |      `large`       |    ~10 GB     |       1x       |
| turbo  |   809 M    |        N/A         |      `turbo`       |     ~6 GB     |      ~8x       |