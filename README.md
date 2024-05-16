# Lane-Detection

<h2>Project Overview</h2>
    <p>This project demonstrates a lane detection system using computer vision techniques in Python with the help of the OpenCV library. The system processes video frames to detect lane lines on roads, which is crucial for developing autonomous driving systems. The resulting video, showcasing detected lanes, is saved to a file for further analysis and visualization.</p>
<img src="https://github.com/Papakobina/Lane-Detection/blob/main/lane_detection_overview.png"/>
    
  <h2>Technology Stack</h2>
    <ul>
        <li><strong>Programming Language</strong>: Python</li>
        <li><strong>Libraries</strong>: OpenCV, NumPy</li>
        <li><strong>Environment</strong>: Any Python-supported environment (Windows, macOS, Linux)</li>
  </ul>
    
<h2>Usage</h2>
    <ol>
        <li>Place your input video in the <code>videos</code> directory.</li>
        <li>Run the script:
            <pre><code>python laneDetection.py</code></pre>
        </li>
        <li>The output video with detected lanes will be saved in the <code>videos</code> directory as <code>lane_detection_output.mp4</code>.</li>
    </ol>

  <h2>Technical Explanation</h2>
    
  <h3>Step-by-Step Process</h3>
    <h4>Reading the Video:</h4>
    <p>The script uses OpenCV's <code>VideoCapture</code> to read frames from the input video.</p>
    
  <h4>Preprocessing:</h4>
    <ul>
        <li><strong>Grayscale Conversion</strong>: Each frame is converted to a grayscale image to simplify the edge detection process.</li>
        <li><strong>Canny Edge Detection</strong>: The grayscale image undergoes edge detection using the Canny algorithm to highlight significant edges.</li>
    </ul>
    
  <h4>Region of Interest (ROI):</h4>
    <p>A mask is created to focus on the lower part of the image where the lanes are expected to be. This reduces noise from irrelevant parts of the frame.</p>
    
  <h4>Hough Line Transform:</h4>
    <p>The processed image is passed through the Hough Line Transform to detect lines in the ROI. This method finds lines by looking for intersections in the parameter space.</p>
    
  <h4>Drawing Lines:</h4>
    <p>Detected lines are drawn on a black image, and then this image is overlaid on the original frame using weighted addition to highlight the lane lines.</p>
        <h4>Saving the Video:</h4>
    <p>Processed frames are written to an output video file using OpenCV's <code>VideoWriter</code>.</p>
    
  <h3>Functions Breakdown</h3>
    
  <h4><code>draw_the_lines(image, lines)</code>:</h4>
    <ul>
        <li>Creates an image with detected lines.</li>
        <li>Draws lines on a blank image and merges it with the original frame.</li>
    </ul>
    
  <h4><code>region_of_interest(image, region_points)</code>:</h4>
    <ul>
        <li>Applies a mask to the image to retain only the region of interest.</li>
        <li>Uses a polygonal mask to focus on the lower triangular region.</li>
    </ul>
    
  <h4><code>get_detected_lanes(image)</code>:</h4>
    <ul>
        <li>Combines the steps of preprocessing, edge detection, ROI masking, and line detection.</li>
        <li>Returns the final image with detected lanes drawn.</li>
    </ul>

  <h2>Next Steps to Improve the Application</h2>
    <h3>Enhance Lane Detection Accuracy:</h3>
    <ul>
        <li>Implement more advanced edge detection techniques.</li>
        <li>Use machine learning models to improve lane detection.</li>
    </ul>

  <h3>Real-time Processing:</h3>
    <ul>
        <li>Optimize the code for real-time lane detection.</li>
        <li>Implement the solution on an embedded system like Raspberry Pi.</li>
    </ul>

  <h3>Additional Features:</h3>
    <ul>
        <li>Detect and annotate lane departure warnings.</li>
        <li>Integrate with other sensor data for more robust autonomous driving systems.</li>
    </ul>

  <h3>GUI Integration:</h3>
    <ul>
        <li>Create a user-friendly interface to load videos and display results.</li>
    </ul>

  <h2>Conclusion</h2>
  <p>This project serves as a foundational implementation of lane detection in autonomous vehicles. By leveraging computer vision techniques, it demonstrates how to preprocess video frames, detect edges, and highlight lanes. Future improvements can build on this foundation to create more sophisticated and robust lane detection systems.</p>
