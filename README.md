# Video Object Tracking with Kalman Filters  

## Overview  
This project implements a **video object tracking system** using **Kalman filters** in Python. The system predicts and corrects the position of an object in real-time by leveraging a mathematical model for motion estimation. This approach is ideal for motion tracking tasks in dynamic environments.  

The project includes:  
- Kalman filter setup and configuration for motion tracking.  
- Real-time prediction of object positions.  
- Visualization of predicted and corrected positions on video frames.  

## Features  
- **Real-Time Tracking**: Processes each video frame and predicts the next object position in real-time.  
- **Prediction and Correction**: Combines motion modeling with real-time measurements to enhance accuracy.  
- **Customizable**: Easily adapt to different motion scenarios by tweaking Kalman filter parameters.  

## Installation  

1. Clone the repository:  
   ```bash  
   git clone https://github.com/ahmdmohamedd/video-object-tracking-kalman-filters.git  
   cd video-object-tracking-kalman-filters  
   ```  

2. Create and activate a virtual environment (optional but recommended):  
   ```bash  
   python -m venv venv  
   source venv/bin/activate  # On Windows: venv\Scripts\activate  
   ```   

3. Ensure OpenCV is installed:  
   If working in a GUI-enabled environment, use the full OpenCV package:  
   ```bash  
   pip install opencv-python  
   ```  
   If working in a headless environment (e.g., Jupyter Notebook), use:  
   ```bash  
   pip install opencv-python-headless  
   ```  

## Usage  

1. Prepare a video file:  
   - Add the path to your video file in the code.  
   - Update the Region of Interest (ROI) manually for the object you wish to track.  

2. Run the notebook:  
   Open the `kalman_tracking.ipynb` file in Jupyter Notebook or an IDE like VSCode, and run the cells step by step.  

3. Viewing the output:  
   - In GUI-enabled environments, the tracked video will display in a window.  
   - In GUI-less environments (e.g., Jupyter), use Matplotlib for visualization or save the output as a video file.  

## Implementation Details  

### 1. **Kalman Filter Setup**  
The Kalman filter is initialized with the following components:  
- **State Vector**: Tracks object position (x, y) and velocity (dx, dy).  
- **Transition Matrix**: Defines the relationship between consecutive states.  
- **Measurement Matrix**: Maps the predicted state to observable quantities.  
- **Covariance Matrices**: Handle process and measurement noise.  

### 2. **Prediction and Correction Cycle**  
- **Prediction**: Based on the current state, predict the next position of the object.  
- **Correction**: Update the state with the actual measured position of the object.  

### 3. **Visualization**  
- Predicted positions are visualized using red circles.  
- Measured positions and tracking regions are shown as green rectangles.  

## Limitations and Notes  
- **Environment Dependency**: The `cv2.imshow` function may not work in Jupyter Notebook due to environment constraints (e.g., Windows 11). Use Matplotlib or save frames to disk instead.  
- **Manual ROI Initialization**: Currently, the ROI for the tracked object must be manually specified.  

## Future Improvements  
- Automate object detection and ROI selection using YOLO or other object detection models.  
- Enhance scalability for multi-object tracking scenarios.  
- Implement advanced trackers like SORT or DeepSORT for better performance.  

## Contribution  
Contributions are welcome! If you'd like to improve this project, please fork the repository, create a branch, and submit a pull request.  


---  
