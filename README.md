Real-Time Multi-Model YOLOv8 Detection
This project demonstrates how to perform real-time object detection using two different Ultralytics YOLOv8 models simultaneously on a single video stream (e.g., a webcam). It leverages Python's threading module to enhance performance and ensure a smooth, non-blocking application.
The detection results from each model are displayed live in their own separate windows.
(Note: The image above is a placeholder. You can replace it with a screenshot or GIF of your own project.)
🌟 Key Features
Simultaneous Model Inference: Runs two different YOLOv8 models concurrently on the same video frame.
Multi-Threaded Architecture:
The video capture process runs on a separate thread to prevent I/O blocking in the main application.
Each model's prediction (inference) process is managed in its own thread for parallel execution.
Separate Display Windows: The results from each model are shown in their own dedicated window to avoid confusion.
Configurable: Easily change model paths, video source, and confidence thresholds.
🏗️ How It Works
The project's architecture relies on three main threads to distribute tasks efficiently:
Video Capture Thread (VideoCaptureThread): This thread continuously reads frames from the video source and stores the latest one in a shared variable. This prevents I/O operations (frame reading) from blocking the main logic.
Model 1 Inference Thread: Within the main loop, a thread is created to run the first YOLO model (e.g., catlak.pt) on the current video frame.
Model 2 Inference Thread: Simultaneously, another thread is created to run the second YOLO model (e.g., bina.pt) on the same video frame.
The main program manages these threads, waits for them to complete, and then draws the results from each model onto their respective OpenCV windows.
🚀 Setup and Getting Started
Follow these steps to run the project on your local machine.
1. Prerequisites
Python 3.8 or newer
pip (Python package installer)
2. Clone the Repository
code
Bash
git clone https://github.com/your-username/your-project-name.git
cd your-project-name
3. Create a Virtual Environment (Recommended)
code
Bash
python -m venv venv
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
4. Install Dependencies
Install the required libraries from a requirements.txt file.
code
Bash
pip install -r requirements.txt
If you don't have a requirements.txt file, you can install them manually:
code
Bash
pip install ultralytics opencv-python
5. Place Your Models
Place your custom-trained YOLOv8 models (with a .pt extension) in the project's root directory. The names specified in the code are:
catlak.pt
bina.pt
If your model files have different names, be sure to update the model1_path and model2_path variables in the script.
💻 Usage
Once the setup is complete, run the application with the following command:
code
Bash
python main.py
(Note: This assumes your Python script is named main.py.)
When the application starts, two windows will open. One will display the "Crack Detection" results, and the other will show the "Building Status" results.
To quit, press the 'q' key on your keyboard while one of the application windows is selected.
⚙️ Configuration
You can easily customize the code to fit your needs:
Change the Video Source:
In the main() function, modify the line: video_thread = VideoCaptureThread(2).
Use 0 for the default webcam.
To process a video file, provide the path as a string: "path/to/your/video.mp4".
Adjust the Confidence Threshold:
In the run_model1 and run_model2 functions, change the conf value in the model.predict() calls.
Example: conf=0.5 (This will only show detections with a confidence score higher than 50%).
📄 License
This project is licensed under the MIT License. See the LICENSE file for details.
