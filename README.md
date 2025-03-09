# AI Emotion Recognition: Analyzing Facial Expressions of World Leaders

![Emotion Analysis](https://img.shields.io/badge/AI-Emotion%20Analysis-blue)
![Python](https://img.shields.io/badge/Python-3.7%2B-green)
![OpenCV](https://img.shields.io/badge/OpenCV-4.5%2B-red)
![DeepFace](https://img.shields.io/badge/DeepFace-0.0.75-orange)

A computer vision project that analyzes facial expressions of political figures to identify emotional patterns throughout video content.

> **Disclaimer:** This analysis is conducted purely for technical demonstration purposes and does not reflect any political preferences or biases. The objective is to showcase AI capabilities in emotion recognition across different speakers, regardless of political affiliation.

## 📋 Overview

This project uses AI to detect and analyze the facial expressions of political figures (including President Zelensky, President Trump, and JD Vance) from video footage. The system processes video frames, identifies faces, and classifies emotional states using deep learning models, providing insights into non-verbal communication patterns during political discourse.

## ✨ Features

- **Multi-person face detection** and tracking using MediaPipe
- **Emotion classification** into 7 categories (happy, sad, angry, disgust, fear, surprise, neutral)
- **Temporal emotion tracking** showing how emotions change over time
- **Comparative analysis** between different speakers
- **Visualization tools** including:
  - Emotion trajectory graphs
  - Face galleries with metadata
  - Emotion distribution charts
  - Annotated summary videos with emotion labels
- **Audio synchronization** in result videos

## 🔧 Installation

```bash
# Clone this repository
git clone https://github.com/yourusername/ai-emotion-recognition.git
cd ai-emotion-recognition

# Create and activate virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Requirements

- Python 3.7+
- OpenCV
- MediaPipe
- DeepFace
- NumPy
- Matplotlib
- tqdm
- FFmpeg (for audio processing)

Full dependencies are listed in `requirements.txt`.

## 🚀 Usage

### Basic Usage

```python
# Analyze a video file
python analyze_video.py --input path/to/video.mp4 --output results/
```

### Advanced Options

```python
# Full options
python analyze_video.py --input path/to/video.mp4 --output results/ --sample-rate 5 --min-faces 10 --generate-video --add-audio
```

## 🧠 How It Works

The emotion analysis pipeline consists of several steps:

1. **Face Detection**: Using MediaPipe's face detection model to identify faces in video frames
2. **Face Extraction**: Cropping and saving detected faces with metadata
3. **Emotion Analysis**: Processing each face with DeepFace to classify emotions
4. **Emotion Tracking**: Following emotional patterns across frames
5. **Visualization**: Generating charts and annotated videos
6. **Audio Integration**: Adding original audio to the analysis video

## 📊 Results

The system generates several outputs:

- **Face Gallery**: Collection of detected faces with ID and appearance counts
- **Emotion Trajectories**: Time-series graphs showing emotion changes
- **Distribution Charts**: Bar charts showing the overall emotional makeup
- **Summary Video**: Annotated video with bounding boxes and emotion labels

Example emotion distribution for one of the analyzed videos:
- Neutral: 54.2%
- Happy: 29.7%
- Sad: 8.5%
- Fear: 4.2%
- Surprise: 2.5%
- Angry: 0.8%

## 📝 Technical Details

### Face Detection

We use MediaPipe's face detection model which offers excellent performance even with varying face angles and lighting conditions. The detector outputs bounding boxes for each detected face, which we use to extract face regions.

### Emotion Recognition

For emotion recognition, we utilize the DeepFace library which implements several deep learning models for facial analysis. The emotion classifier categorizes expressions into seven basic emotions and provides confidence scores for each category.

### Video Processing

Video processing is handled with OpenCV, which allows efficient frame extraction and manipulation. To optimize processing time, we sample frames at regular intervals rather than processing every frame.

## 🔮 Future Improvements

- Improve face tracking across frames to better maintain identity
- Add speech emotion analysis using audio processing
- Implement more sophisticated emotion models for better accuracy
- Create interactive visualization dashboard
- Add support for real-time analysis of live video streams

## 🙏 Acknowledgments

- [MediaPipe](https://google.github.io/mediapipe/) for their excellent face detection models
- [DeepFace](https://github.com/serengil/deepface) for providing pre-trained emotion recognition models
- [OpenCV](https://opencv.org/) for computer vision capabilities

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
