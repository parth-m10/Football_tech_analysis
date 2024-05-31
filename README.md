# Football Video Analysis

This project aims to develop a computer vision-based system for analyzing football matches from video footage. The primary goals are to track players, referees, and the ball; measure their movements and speeds; and analyze possession time for each team.

## Features

1. **Object Detection and Tracking**
   - Detect and track football players, referees, and the ball using YOLOv5 and object tracking algorithms.
   - Utilize a labeled dataset of football players and referees from Roboflow for training the object detection model.
   - Employ techniques like Bite Tracker and visual feature matching to maintain consistent object IDs across frames.

2. **Movement Analysis**
   - Measure the distance covered and speed of players, referees, and the ball using optical flow and camera movement estimation.
   - Estimate camera motion and compensate for it to obtain accurate movement measurements in real-world units (e.g., meters).

3. **Ball Possession Analysis**
   - Analyze ball possession for each team throughout the match.
   - Visualize ball control statistics as an overlay on the video frames.

4. **Interpolation and Prediction**
   - Interpolate ball positions in frames where it is not detected.
   - Predict ball movement to enhance tracking accuracy.

## Prerequisites

- Python 3.7 or higher
- OpenCV
- PyTorch
- YOLOv5
- Roboflow (for accessing the football player dataset)

## Installation

1. Clone the repository:
   ```
   git clone https://github.com/your-username/football-video-analysis.git
   ```

2. Install the required packages:
   ```
   pip install -r requirements.txt
   ```

3. Download the football player dataset from Roboflow and place it in the `data/` directory.

## Usage

1. Train the object detection model:
   ```
   python train.py --data data/football_dataset.yaml --weights yolov5s.pt --batch-size 16
   ```

2. Run the video analysis script:
   ```
   python analyze_video.py --video path/to/your/video.mp4 --weights path/to/trained/weights.pt
   ```

   This will process the video, track objects, measure movements, and analyze ball possession. The results will be displayed in real-time and can be saved as a new video file.

## Contributing

Contributions to this project are welcome! If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.


## Acknowledgments

- [YOLOv5](https://github.com/ultralytics/yolov5) for the object detection model.
- [Roboflow](https://roboflow.com/) for the football player dataset.
- [OpenCV](https://opencv.org/) for computer vision and image processing.
