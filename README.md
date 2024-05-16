This project converts a disparity image into a 3D point cloud using predefined camera parameters and transformations. The process involves several steps to ensure accurate and meaningful 3D reconstruction.

First, the disparity image is loaded using OpenCV, and depth values are calculated using the formula `Z = (f * b) / d`, where `f` is the focal length, `b` is the baseline, and `d` is the disparity value. Valid depth values are extracted to generate corresponding x, y, and z coordinates in the world frame.

Next, the 3D point cloud is visualized using Plotly, providing an interactive 3D scatter plot. The coordinates are saved in a CSV file (`pcd_world.csv`) for further analysis.

The point cloud is then transformed into the camera frame by adjusting the coordinates based on the intrinsic parameters of the camera. These transformed coordinates are saved as `pcd_camera.csv` and also visualized using Plotly.

Finally, the coordinates are transformed into the robot frame using a homogeneous transformation matrix that includes rotation and translation parameters. The resulting point cloud is saved as `pcd_robot.csv` and visualized using Matplotlib, highlighting the depth with a color bar.

This comprehensive approach allows for detailed analysis and visualization of 3D point clouds in different reference frames, facilitating various applications in robotics and computer vision.
