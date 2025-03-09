# AI Emotion Recognition: Facial Expression Analysis of World Leaders

![Emotion Analysis](https://img.shields.io/badge/AI-Emotion%20Analysis-blue)
![Python](https://img.shields.io/badge/Python-3.7%2B-green)
![OpenCV](https://img.shields.io/badge/OpenCV-4.5%2B-red)
![DeepFace](https://img.shields.io/badge/DeepFace-0.0.75-orange)
![MediaPipe](https://img.shields.io/badge/MediaPipe-0.8.9-purple)

An advanced computer vision project that analyzes facial expressions of political figures in real-time, revealing emotional patterns hidden beneath public appearances. This system combines facial detection, emotion recognition, and temporal tracking to provide insights into non-verbal communication during political speeches and interviews.

> **Disclaimer:** This analysis is conducted purely for technical demonstration purposes and does not reflect any political preferences or biases. The objective is to showcase AI capabilities in emotion recognition across different speakers, regardless of political affiliation.

## 📋 Overview

This project uses state-of-the-art AI to detect and analyze the facial expressions of political figures (including President Zelensky, President Trump, and JD Vance) from video footage. Going beyond simple frame-by-frame detection, the system implements:

- Robust face tracking with persistence across frames
- Temporal emotion smoothing to filter noise and capture true expressions
- Color-coded visualizations with confidence indicators
- Multi-person differentiation and parallel tracking

The result is a comprehensive analysis revealing how emotions evolve throughout speeches and interviews, providing unique insights into the emotional landscape of political communication.

## ✨ Key Features

- **Advanced Face Detection & Tracking**
  - Multiple person tracking with identity persistence 
  - Stable bounding boxes with reduced flickering
  - Handles temporary occlusion and pose changes
  
- **Sophisticated Emotion Analysis**
  - Classification into 7 distinct emotions (happy, sad, angry, disgust, fear, surprise, neutral)
  - Confidence percentages for each detected emotion
  - Rolling-window approach for temporal consistency
  
- **Rich Visualizations**
  - Color-coded emotion indicators (green=happy, red=angry, etc.)
  - Time-series emotion trajectories
  - Face galleries with appearance counts
  - Distribution analysis of emotional states
  
- **Enhanced Video Generation**
  - Annotated footage with emotion labels
  - Audio synchronization with voice analysis
  - Multiple codec support for cross-platform compatibility

## 🚀 Getting Started

### Quick Start

Simply download the Jupyter notebook and run it:

```bash
# Clone this repository (if using Git)
git clone https://github.com/yourusername/emotion-analysis.git
cd emotion-analysis

# Download your video (outside from this ipynb) to your current dir, you could try:
pip install yt-dlp
yt-dlp -f "best[height<=720]" "https://www.youtube.com/watch?v=v_kTNIYsFnQ" -o "test_video.mp4"

# Drop the video to the notebook environment
# Open and run the notebook
jupyter notebook emotion_analysis.ipynb


```

### Analyzing Your Own Videos

There are two ways to analyze videos:

1. **From YouTube**: Modify the URL in this line:
   ```python
   video_path = download_video("https://www.youtube.com/watch?v=v_kTNIYsFnQ", "test_video.mp4")
   ```

2. **From Local File**: Upload your own video and rename it to `test_video.mp4`

### Requirements

- Python 3.7+
- OpenCV
- MediaPipe
- DeepFace
- NumPy
- Matplotlib
- tqdm
- FFmpeg (for audio processing)

## 🧠 How It Works

### Processing Pipeline

The system operates through a sophisticated multi-stage pipeline:

1. **Video Input Processing**
   - Frame extraction at optimal intervals
   - Resolution normalization
   - Metadata preservation

2. **Face Detection & Tracking**
   - MediaPipe face detection model identifies faces in each frame
   - IOU (Intersection over Union) tracking maintains identity across frames
   - Persistence mechanism keeps tracks alive through brief disappearances

3. **Emotion Analysis**
   - DeepFace performs emotion classification on each detected face
   - Temporal smoothing applies a rolling window to filter noise
   - Confidence calculation based on emotion consistency

4. **Visualization Generation**
   - Emotion trajectories plotted as time-series data
   - Face galleries created with metadata
   - Distribution charts show overall emotional makeup

5. **Enhanced Video Creation**
   - Original video annotated with emotion labels and bounding boxes
   - Color-coding applied based on emotion type
   - Voice analysis (optional) adds audio emotional context

## 🔍 Technical Innovations

### Stable Face Tracking

The system implements a tracking algorithm that:
- Uses IOU (Intersection over Union) to match faces across frames
- Maintains identity even when faces temporarily disappear
- Requires only 30% overlap between frames for successful tracking
- Keeps tracks alive for up to 1.5 seconds after disappearance

### Temporal Emotion Smoothing

To reduce noise and capture true emotional states:
- Implements a 0.5-second rolling window for each face
- Uses Counter-based frequency analysis to determine dominant emotions
- Calculates confidence scores based on consistency
- Adjusts visualization intensity based on confidence percentage

### Multi-Codec Video Support

To ensure videos work across platforms:
- Attempts multiple codecs (H264, XVID, mp4v) in sequence
- Includes a direct FFmpeg fallback option
- Verifies video creation success with file checking
- Provides detailed error handling for troubleshooting

## 📊 Example Results

Analysis of political figures reveals distinctive emotional patterns:

- **Emotion Distribution Example**:
  - Neutral: 54.2%
  - Happy: 29.7%
  - Sad: 8.5% 
  - Fear: 4.2%
  - Surprise: 2.5%
  - Angry: 0.8%

- **Insights**:
  - Political figures maintain predominantly neutral expressions during formal addresses
  - Emotional transitions often correlate with topic changes
  - Brief microexpressions provide windows into potentially concealed emotions
  - Distinct emotional "signatures" can be observed for different speakers

## 🔮 Future Development

- Real-time analysis capabilities for live broadcasts
- Deeper speech-emotion correlation analysis
- Integration with speech recognition for text-emotion alignment
- Expansion to multi-cultural expression analysis
- Machine learning models to predict upcoming emotional shifts

## 🙏 Acknowledgments

- [The Telegraph](https://www.youtube.com/watch?v=v_kTNIYsFnQ&list=PPSV) for the original video content used in this analysis
- [My YouTube demonstration](https://www.youtube.com/watch?v=eltbniewHys&t=1s) for the full project walkthrough
- [MediaPipe](https://google.github.io/mediapipe/) for their excellent face detection models
- [DeepFace](https://github.com/serengil/deepface) for providing pre-trained emotion recognition models
- [OpenCV](https://opencv.org/) for computer vision capabilities
- The research community advancing facial expression analysis techniques

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
