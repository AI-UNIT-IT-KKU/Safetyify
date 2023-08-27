# SafetyThon

## Dual YOLO Object Detection

This repository contains code for dual object detection using two YOLO models in sequence. The first model detects humans, and if a human is detected, the second model identifies objects such as hardhats, masks, safety vests, and more.

## How It Works

1. The first YOLO model, `yolov8l.pt`, is used to detect humans in the video stream.
2. If a human is detected, the second YOLO model, `best.pt`, activates to recognize specific objects or attributes.
3. The recognized objects are highlighted with bounding boxes, each having a different color for easy distinction.

## Prerequisites

- Python 3.8
- OpenCV
- Ultralytics YOLO

## Setup

1. Clone the repository:
    ```bash
    git clone [Repo URL]
    cd [Repo Name]
    ```

2. Install the required packages:
    ```bash
    pip install opencv-python ultralytics
    ```

3. Place your input video as `vid/test.mp4` or modify the source path in the code.

4. Make sure you have the model weights (`yolov8l.pt` and `best.pt`) in the root directory.

## Running the Detector

> **Note for Windows Users**: If you are working on Windows, change `device="mps"` to your GPU (e.g., `"cuda:0"`) if you have one, or `"cpu"` if you don't.

Execute the detection script:

```bash
python Safty.py
```

The processed video will be saved as `output_detect.mp4` in the root directory.

## Customization

- **Model Weights**: You can replace `yolov8l.pt` and `best.pt` with your own trained weights if required.
- **Class Colors**: Colors for bounding boxes are predefined for each class. They can be modified in the `colors` dictionary.

## Output

Detected objects are highlighted using colored bounding boxes. The class and the confidence score are displayed on top of each bounding box.

