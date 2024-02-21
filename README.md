# Cobot Basics

A Python library simplifying the essential concepts and techniques for working with collaborative robots (cobots).

## **Key Features**

- **Communication:** Establishes smooth communication with your cobot using common protocols:
  - TCP/IP socket-based communication
  - Modbus for interfacing with industrial devices
- **Path Planning:** Implement straightforward path planning algorithms:
  - Linear interpolation for basic point-to-point motion
  - Joint-space motion for direct control of joint angles
- **Camera Integration:** Seamlessly integrate camera systems for enhanced cobot functionality:
  - OpenCV support for image processing and computer vision tasks
  - Examples for object detection and pose estimation

## **Getting Started**

1. **Install the library:**

   ```bash
   pip install cobotics
   ```

2. **Connect to your cobot:** Refer to your cobot's manual for connection instructions. An example with TCP/IP:

   ```python
   import cobotics as cb
   import socket

   cobot_ip = "192.168.1.100"  # Replace with your cobot's IP address
   cobot_port = 30002  # Replace if needed

   cobot = cb.Cobot(cobot_ip, cobot_port)
   cobot.connect()
   ```

3. **Start exploring!** Check out the examples folder for practical demonstrations.

**Example: Moving the Cobot**

```python
import cobotics as cb

# ... (Connection code from above) ...

target_point = [0.4, 0.2, 0.3]  # Example coordinates (meters)
cobot.move_linear(target_point)
```

**Camera Usage Example**

```python
import cobot_basics as cb
import cv2 # Make sure you have OpenCV installed (pip install opencv-python)

# ... (Connection code) ...

camera = cb.Camera()
image = camera.capture_image()

# Use OpenCV for tasks like object detection:
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
objects = my_object_detector.detect(gray)
```

## **Disclaimer:**

This library is intended for educational and prototyping purposes. Ensure you thoroughly understand your specific cobot, its safety features, and industrial safety standards before operating it in real-world scenarios.

## **Contributing**

We welcome contributions to expand the capabilities of 'cobotics'! Feel free to submit pull requests or open issues for feature requests and bug reports.

**Let's build a fantastic foundation for cobot development with Python!**

Let me know if you'd like any modifications or have specific aspects you want to highlight!
