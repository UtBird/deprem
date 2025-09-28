---

# 🏗️ YOLO for Crack and Building Condition Detection

This project uses **Python**, **OpenCV**, and **Ultralytics YOLO** to perform real-time detection of **cracks** and **building conditions** from live video streams. With multithreading and real-time video processing, it delivers high-performance results.

## 📁 Project Structure

```
yolo-dual-detection/
├── catlak.pt        # YOLO model for crack detection
├── bina.pt          # YOLO model for building condition detection
├── main.py          # Main application file
├── README.md        # Project documentation
```

## ⚙️ Features

* 🧠 **Dual Model Support**: Runs two YOLO models simultaneously (crack + building).
* 🎥 **Real-Time Video**: Processes input from a camera or external video source.
* ⚡ **Multithreading**: Each model runs in a separate thread for better performance.
* 🖼️ **Live Visualization**: Results are displayed in separate windows with bounding boxes and labels.

## 🧩 Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/UtBird/yolo-dual-detection.git
   cd yolo-dual-detection
   ```

2. **Install Dependencies**

   Requires **Python 3.8+**. Install the required libraries:

   ```bash
   pip install ultralytics opencv-python
   ```

## 🚀 Usage

1. **Run the Main Application**

   ```bash
   python main.py
   ```

   This command will start processing video input and run both models simultaneously.

2. **Change Video Source**

   In the code, the video source is defined as:

   ```python
   video_thread = VideoCaptureThread(2)
   ```

   * `0` → Default system camera
   * `1` → External camera
   * `2` → Other sources

   Adjust according to your setup.

3. **Exit**

   Press **q** while the program is running to exit.

## 📊 Output

* **Crack Detection Window** → Displays detected cracks.
* **Building Condition Window** → Displays building condition analysis results.
* Bounding boxes are drawn in **pink** (`(255, 0, 102)`).

---
