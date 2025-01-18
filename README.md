# Subtitle Generator

A deep learning-based subtitle generation system that creates subtitles for videos by processing audio through a hybrid CNN-LSTM architecture.

## Abstract

This project develops an end-to-end subtitle generation system that:
- Takes YouTube video URLs as input
- Downloads and processes videos using YT-DLP
- Extracts audio using FFmpeg
- Converts audio into spectrograms using Librosa
- Processes spectrograms through a CNN-LSTM model
- Generates synchronized subtitles

The system uses a hybrid CNN-LSTM architecture to convert audio spectrograms into text, incorporating features like temporal processing and character-level prediction.

## Methodology

### Problem Statement
Modern subtitle generators are essential for:
- Making content accessible to deaf/hard-of-hearing individuals
- Supporting non-native speakers
- Enabling content consumption in noisy environments
- Facilitating cross-language content delivery


### Data Collection and Preprocessing

#### Dataset
- Using [LibriSpeech dataset](https://www.openslr.org/12)
- ~1000 hours of English speech
- Clean, segmented audiobook recordings
- Organized by speaker and chapter
- Used train-clean-100 subset for development

#### Preprocessing Steps
1. Audio processing:
   - FLAC to spectrogram conversion
   - Speaker and chapter organization
   - Transcript matching
2. Data organization:
   - File ID extraction
   - Speaker/chapter mapping
   - Transcript alignment

### Model Architecture

#### CNN Layers
- Multiple convolutional layers (64, 128, 256, 512 filters)
- LeakyReLU activation
- Batch normalization
- MaxPooling
- Dropout (20%)

#### LSTM Processing
- Bidirectional LSTM layers
- 512 and 256 units respectively
- 30% dropout rate
- TimeDistributed output layer

#### Training Parameters
- Batch size: 16
- Epochs: 20
- Optimizer: Adam
- Loss: Categorical Cross-entropy

## Results

Current model performance:
- Word Error Rate (WER): 0.98
- Model predictions require improvement
- Base architecture implemented successfully

## Alternative Implementation

A successful implementation was achieved using pre-trained models:
1. OpenAI's Whisper for transcription
2. FFmpeg for subtitle overlay
3. YT-DLP for video downloading

## Challenges Faced

1. Technical Limitations:
   - Limited GPU resources
   - Dataset size constraints
   - Model architecture optimization

2. Performance Issues:
   - High Word Error Rate
   - Architecture tuning difficulties
   - Resource constraints

## Future Scope

1. Technical Improvements:
   - Reduce Word Error Rate
   - Implement advanced encoding techniques
   - Optimize model architecture

2. Feature Additions:
   - Noise resistance capabilities
   - Multilingual support
   - Real-time processing

## Dependencies

```python
tensorflow
keras
numpy
pandas
librosa
ffmpeg
yt-dlp
```

[Previous sections remain the same until References]

## References

1. [YouTube Playlist - Audio Processing Tutorials](https://youtube.com/playlist?list=PLKnIA16_RmvYuZauWaPlRTC54KxSNLtNn)
2. [YouTube Tutorial on Audio Processing](https://youtu.be/ZLIPkmmDJAc)
3. [Kaggle Notebook - LibriSpeech Implementation](https://www.kaggle.com/code/heiswicked/libri-01)
4. [Deep Audio Classification GitHub Repository](https://github.com/nicknochnack/DeepAudioClassification/blob/main/AudioClassification.ipynb)
5. [YouTube Tutorial - Audio Processing Guide](https://www.youtube.com/watch?v=dJYGatp4SvA)
6. [Audio Deep Learning Made Simple - Towards Data Science](https://towardsdatascience.com/audio-deep-learning-made-simple-part-1-state-of-the-art-techniques-da1d3dff2504)
7. [Speech Recognition with Neural Networks - GitHub](https://github.com/vrnanshuman/speech-recognition-with-nn/blob/main/vui_notebook.ipynb)
8. [Research Paper on Speech Recognition](https://www.sciencedirect.com/science/article/pii/S1877050924006227)
9. [History of Subtitles - SubtitleBee](https://subtitlebee.com/blog/history-of-subtitles)
10. [AI for Subtitles Guide - AmberScript](https://www.amberscript.com/en/blog/ai-for-subtitles-for-videos-guide)
11. [LibriSpeech ASR Corpus](https://www.openslr.org/12)
12. [Audio Signal Processing with Spectrograms](https://khareanu1612.medium.com/audio-signal-processing-with-spectrograms-and-librosa-b66a0a6bc5cc)
13. [One-Hot Encoding Guide - GeeksforGeeks](https://www.geeksforgeeks.org/ml-one-hot-encoding)
14. [Sparse Matrix in Machine Learning - GeeksforGeeks](https://www.geeksforgeeks.org/sparse-matrix-in-machine-learning)
15. [LSTM vs GRU Comparison](https://medium.com/@prudhviraju.srivatsavaya/lstm-vs-gru-c1209b8ecb5a)
16. [Regularization in Machine Learning - GeeksforGeeks](https://www.geeksforgeeks.org/regularization-in-machine-learning)

