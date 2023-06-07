# Speech-to-Speech Summarization in Deep Learning

This repository contains code for a speech-to-speech summarization project using deep learning techniques. The goal of this project is to summarize speech content and generate a concise summary.

## Repository Specifications

- Repository: [https://github.com/armansouri9/speech-to-speech-summarization-in-deep-learning](https://github.com/armansouri9/speech-to-speech-summarization-in-deep-learning)

## Code

The code provided in this repository performs the following tasks:

1. Mounts Google Drive:
```python
from google.colab import drive
drive.mount('/content/drive')
```

2. Imports the required libraries:
```python
from vosk import Model, KaldiRecognizer
from pydub import AudioSegment
```

3. Installs the `vosk` library:
```python
!pip install vosk
```

4. Installs the `pydub` library:
```python
!pip install pydub
```

5. Loads the Vosk model and sets up the recognizer:
```python
FRAME_RATE = 16000
CHANNELS = 1

model = Model(model_name="vosk-model-en-us-0.22")
rec = KaldiRecognizer(model, FRAME_RATE)
rec.SetWords(True)
```

6. Accepts an audio waveform and performs speech recognition:
```python
mp3 = AudioSegment.from_mp3("/content/drive/MyDrive/s2s/marketplace_full.mp3")
mp3 = mp3.set_channels(CHANNELS)
mp3 = mp3.set_frame_rate(FRAME_RATE)

rec.AcceptWaveform(mp3.raw_data)
result = rec.Result()

import json
text = json.loads(result)["text"]
```

7. Installs the `transformers` library:
```python
!pip install transformers
```

8. Installs the `torch` library:
```python
!pip install torch -f https://download.pytorch.org/whl/torch_stable.html
```

Please refer to the code files in the repository for more details.

**Note:** Some code snippets in the provided code block are commented out. You may uncomment them if needed.

For more information and usage instructions, please refer to the repository [README](https://github.com/armansouri9/speech-to-speech-summarization-in-deep-learning/README.md).

Please make sure to follow the code's licensing terms and conditions provided by the repository owner.

## License

This project is licensed under a Free License.
