# Multiple Object Tracking (MOT) in Self-Driving Cars

## Introduction
This document highlights the significance of Multiple Object Tracking (MOT) over Single Object Tracking (SOT) for self-driving vehicles. MOT's ability to track multiple objects simultaneously is critical for the safe navigation of autonomous vehicles.

## Key Takeaways

### MOT vs. SOT
- **MOT** tracks numerous objects in parallel, crucial for autonomous driving scenarios.
- **SOT** focuses on tracking individual objects, less complex but limited in dynamic environments.

### Core MOT Techniques
1. **Object Detection**: Pinpoint objects within a frame using models like YOLOv7.
2. **Unique ID Assignment**: Each object's bounding box receives a unique identifier.
3. **Object Tracking**: Use estimation algorithms to predict and maintain object movement and IDs across frames.

### DeepSORT Algorithm
- Combines deep learning with traditional tracking methods.
- **Components**:
  - **Bounding Box Prediction**: Initial detection using object detection algorithms.
  - **State Estimation**: Kalman filter application for predicting future positions.
  - **Target Association**: Resolves ambiguities using a matching cascade and Hungarian algorithm.
  - **Mahalanobis Distance and Deep Appearance Descriptor**: Helps manage occlusions and ID persistence.

### StrongSORT Algorithm
- An advanced version of DeepSORT with several improvements:
  - **Improved Appearance Descriptor**: Uses BoT+ResNeSt50 for enhanced performance.
  - **Refined Matching**: Incorporates EMA for better matching and efficiency.
  - **Enhanced Correlation Coefficient (ECC)**: Addresses camera motion and lighting variations.
  - **Noise Scale Adaptive (NSA) Kalman Filter**: Adapts dynamically to the quality of detections.
  - **Vanilla Global Linear Assignment**: Aims to improve matching outcomes.

### Implementation
- **StrongSORT**: Applicable to various real-world scenarios like self-driving cars. Utilizes pre-trained models and custom datasets effectively.

### MCMOT Dataset
- A multi-camera, multi-object tracking dataset essential for training and testing MOT systems. Provides extensive labeled data across multiple camera views.

### Model Selection
- **Object Detection**: YOLOv5m recommended for initial detection.
- **Tracking**: osnet_x0_25_market1501 weights suggested for use within the StrongSORT framework.

## Conclusion
StrongSORT shows promising capabilities for MOT in autonomous driving, enhancing both safety and efficiency. Open-source resources are available for further development and research.

