This project develops a real-time perception system for autonomous vehicles by integrating lane detection and object detection techniques. The system processes video input from a camera or recorded footage to identify road lanes and detect surrounding objects such as vehicles and pedestrians. Lane detection is implemented using computer vision techniques with **OpenCV**, which applies image processing methods such as edge detection, region of interest masking, and Hough transforms to determine lane boundaries. For object detection, the system utilizes the deep learning model **YOLOv5** built on the **PyTorch** platform to recognize and classify objects in real time. The combined perception pipeline enables the system to understand the driving environment by simultaneously identifying road structure and dynamic obstacles. This project demonstrates core concepts used in modern autonomous driving systems and provides a practical implementation of computer vision and deep learning techniques for intelligent transportation and driver-assistance applications.

# Integrated Object & Lane Detection (YOLOv5 Optimized)

An optimized computer vision pipeline that combines **YOLOv5 real-time object detection** with **Hough Transform-based lane tracking**. This repository has been specifically refactored to support **Python 3.13+**, **NumPy 2.0+**, and **Apple Silicon (M1/M2/M3)** environments.

## 🚀 Key Modernizations (My Contributions)
Unlike the original legacy versions, this repository includes critical patches to run on the latest Python stacks:
*   **Python 3.13 Support:** Fixed the `ModuleNotFoundError: No module named 'pkg_resources'` by bypassing legacy `setuptools` checks.
*   **NumPy 2.0 Compatibility:** Resolved `AttributeError` for deprecated `np.int` and `np.trapz` (updated to `int` and `np.trapezoid`).
*   **PyTorch 2.6+ Security Fixes:** Patched `torch.load` calls with `weights_only=False` to allow loading legacy `.pt` and `.cache` files safely.
*   **macOS Optimization:** Configured for seamless execution on MacBook Air/Pro via CPU/MPS backends.

## 🛠 Features
*   **Object Detection:** Identifies 80+ classes (cars, pedestrians, traffic lights) using the YOLOv5s architecture.
*   **Lane Detection:** Real-time lane line extraction using Grayscale conversion, Gaussian Blur, Canny Edge Detection, and Hough Line Transformation.
*   **Integrated Inference:** A unified pipeline that draws both bounding boxes and lane overlays on a single video stream.

## 💻 Installation

1. **Clone the Repository:**
   ```bash
   git clone https://github.com
   cd YOLOv5-with-Lane-Detection
Use code with caution.

Create a Virtual Environment:
bash
python3 -m venv venv
source venv/bin/activate
Use code with caution.

Install Dependencies:
bash
pip install -r requirements.txt
pip install setuptools pandas tqdm requests
Use code with caution.

🏃 Usage
Run on Video
bash
python detect.py --source runs/video/Drive_01.mp4 --device cpu
Use code with caution.

Run on Webcam
bash
python detect.py --source 0 --device cpu
Use code with caution.

View Results
Detection outputs, including processed videos and statistical charts, are automatically saved to:
runs/detect/exp_detect/

📊 Performance
Model	Size	mAP@.5	Speed (MacBook Air CPU)
YOLOv5s	640	55.4	~130ms / frame

📜 Acknowledgments & Licensing
Object Detection Core: Ultralytics YOLOv5 (GPL-3.0 License).
Lane Detection: Based on Digital Image Processing (DIP) principles and Hough Transform.
Maintenance: Modernized and patched by:

```markdown
## 👤 Author

**Avyukt**
*   GitHub:  (https://github.com/avyuktcodes)
*   Project: (https://github.com/avyuktcodes/Autonomous-Vehicle-Perception-System)

Feel free to star ⭐ this repository if you found it helpful!