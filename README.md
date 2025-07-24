# Real-Time YOLOv8 Object Detection

This project performs object detection on video files using the pre-trained YOLOv8 model from [Ultralytics](https://github.com/ultralytics/ultralytics) and OpenCV. It processes each frame, draws bounding boxes and labels for detected objects, and saves the result as a new video.

## Features

- Loads YOLOv8 pre-trained model (`yolov8n.pt`)
- Accepts input video files for detection
- Configurable confidence threshold
- Draws bounding boxes and labels on detected objects
- Outputs a processed video file with visualized detections
- Supports Google Colab file upload/download and local execution

## Requirements

- Python 3.x
- [ultralytics](https://pypi.org/project/ultralytics/)
- [opencv-python-headless](https://pypi.org/project/opencv-python-headless/)

Install dependencies:
```sh
pip install ultralytics opencv-python-headless
```

## Usage

### In Google Colab

1. Run the notebook or script.
2. Upload a video file when prompted.
3. The script will process the video and provide a download link for the result.

### Locally

1. Modify the `__main__` section in the script to specify your input and output video file paths:
    ```python
    if __name__ == "__main__":
        input_video_file = "path/to/your/video.mp4"
        output_video_file = "output_result.mp4"
        object_detection_video(input_video_file, output_video_file)
    ```
2. Run the script:
    ```sh
    python Real_Time_YOLO_Object_Detection.ipynb
    ```
    *(Or convert to .py and run with Python)*

3. Check the output video for detections.

## Parameters

- `input_path` (str): Path to the input video file.
- `output_path` (str): Path to save the output video file.
- `confidence_threshold` (float): Minimum confidence score for detections (default: 0.5).

## How It Works

1. Loads the YOLOv8 model.
2. Opens the input video and reads frames.
3. Runs object detection on each frame.
4. Draws bounding boxes and labels for objects above the confidence threshold.
5. Writes processed frames to the output video.
6. Releases resources and (in Colab) offers a download link.

## Notes

- The script is Colab-friendly but can be adapted for local use.
- Ensure the input video file path is valid.
- Processing speed depends on hardware (GPU recommended).
- Adjust the confidence threshold as needed.

## Acknowledgements

- Uses [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics) for object detection.
- Relies on OpenCV for video processing.