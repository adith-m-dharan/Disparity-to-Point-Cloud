# Overview

This project converts a disparity image into a 3D point cloud using predefined camera parameters and transformations. The process involves several steps to ensure accurate and meaningful 3D reconstruction.

First, the disparity image is loaded using OpenCV, and depth values are calculated using the formula $ Z = \frac{f_x \cdot b}{d}$, where \texttt{f\_x} is the focal length in the x direction, \texttt{b} is the baseline, and \texttt{d} is the disparity value. Valid depth values are extracted to generate corresponding x, y, and z coordinates in the world frame.

Next, the 3D point cloud is visualized using Plotly, providing an interactive 3D scatter plot. The coordinates are saved in a CSV file (\texttt{pcd\_world.csv}) for further analysis.

The point cloud is then transformed into the camera frame by adjusting the coordinates based on the intrinsic parameters of the camera. These transformed coordinates are saved as \texttt{pcd\_camera.csv} and visualized using Plotly with a different color scheme for better distinction.

Finally, the coordinates are transformed into the robot frame using a homogeneous transformation matrix that includes rotation and translation parameters. The resulting point cloud is saved as \texttt{pcd\_robot.csv} and visualized using Matplotlib, highlighting the depth with a color bar.

This comprehensive approach allows for detailed analysis and visualization of 3D point clouds in different reference frames, facilitating various applications in robotics and computer vision.
