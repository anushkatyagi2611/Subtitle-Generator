# Subtitle Generator

A deep learning-based system for automatically generating subtitles from video content. The project uses a hybrid CNN-LSTM architecture to convert audio spectrograms into text, creating synchronized subtitles for videos.

## Overview

This project aims to create an end-to-end subtitle generation system that:
- Takes YouTube video URLs as input
- Downloads and processes videos
- Extracts audio content
- Converts speech to text using deep learning
- Synchronizes generated subtitles with video

## Architecture

The system employs a hybrid CNN-LSTM architecture:
- Convolutional Neural Networks (CNNs) for processing audio spectrograms
- Long Short-Term Memory Networks (LSTMs) for sequential text prediction
- Time-distributed output layers for character-level prediction
- Batch normalization and dropout for regularization

### Key Components

1. **Audio Processing**
   - Audio extraction using FFmpeg
   - Spectrogram generation with Librosa
   - Normalization and preprocessing

2. **Text Processing**
   - Character-level one-hot encoding
   - Sequence padding and normalization
   - Word error rate (WER) calculation

3. **Neural Network**
   - Multiple CNN layers (64, 128, 256, 512 filters)
   - Bidirectional LSTM layers
   - TimeDistributed output layer
   - Optimization using Adam

## Dataset

The model is trained on the LibriSpeech dataset:
- Clean speech audio recordings
- Corresponding text transcriptions
- Organized by speaker and chapter
- Train-clean-100 subset used for initial development

## Requirements

```
tensorflow
keras
numpy
pandas
librosa
ffmpeg
yt-dlp
```

## Current Status

The project is in development with some limitations:
- Current WER: 0.98
- Prediction accuracy needs improvement
- Real-time subtitle overlay functionality pending

## Future Improvements

1. **Performance Enhancement**
   - Reduce Word Error Rate
   - Improve model architecture
   - Implement better encoding techniques

2. **Feature Additions**
   - Noise resistance
   - Multilingual support
   - Real-time processing

3. **Technical Improvements**
   - GPU optimization
   - Larger dataset utilization
   - Advanced architecture exploration

## Alternative Implementation

A working version using pre-trained models has been developed using:
1. Whisper by OpenAI for transcription
2. FFmpeg for subtitle overlay
3. YT-DLP for video downloading

## References

- [History of Subtitles](https://subtitlebee.com/blog/history-of-subtitles)
- [AI for Subtitles Guide](https://www.amberscript.com/en/blog/ai-for-subtitles-for-videos-guide)
- [LibriSpeech Dataset](https://www.openslr.org/12)
- [Audio Signal Processing with Spectrograms](https://khareanu1612.medium.com/audio-signal-processing-with-spectrograms-and-librosa-b66a0a6bc5cc)
- [One-Hot Encoding Guide](https://www.geeksforgeeks.org/ml-one-hot-encoding)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

[Add your chosen license here]
