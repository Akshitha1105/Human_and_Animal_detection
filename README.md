# Human & Animal Detection System #

📖 Overview

This project implements a two-stage computer vision pipeline to detect and classify humans and animals in images and videos under real-world deployment constraints. The system uses separate object detection and classification models to improve modularity, interpretability, and performance.

The architecture follows a detection–then–classification paradigm, ensuring flexibility and extensibility for industrial applications.

🎯 Objective

The goal of this system is to:

Detect objects in an image/video frame

Classify each detected object as Human or Animal

Process videos automatically

Generate annotated outputs

Maintain modular design for scalability

🧠 System Architecture

The system consists of two independent models:

Object Detection Model – Faster R-CNN with ResNet-50 FPN

Classification Model – EfficientNet-B0

This separation ensures flexibility and improved decision refinement.

🔍 Why Faster R-CNN?

Algorithm Used: Faster R-CNN (ResNet-50 FPN backbone)

Why it was selected:

Region Proposal Network (RPN) improves detection precision

Anchor-based approach is robust to scale variations

Strong performance on small and medium objects

Suitable for offline inference

Well-validated architecture in industrial systems

Unlike YOLO (which was restricted), Faster R-CNN provides:

Higher localization accuracy

Better bounding box refinement

Improved interpretability in industrial workflows

The Feature Pyramid Network (FPN) enables multi-scale feature extraction, making it robust against varying object sizes in video streams.

🧠 Why Separate Classification Model?

Instead of training the detector for final class prediction, a separate classifier (EfficientNet-B0) was used.

Advantages:

Modular pipeline design

Easier retraining for new categories

Better feature specialization

Improved error correction

EfficientNet-B0 was chosen because:

Excellent accuracy-to-parameter ratio

Efficient inference

Lightweight architecture

Scalable compound scaling principle

This design mirrors real-world deployment systems where detection and classification are decoupled for maintainability.

🎥 Inference Pipeline

Frame extraction from video

Object detection using Faster R-CNN

Cropping detected regions

Classification using EfficientNet

Annotating frames

Saving outputs to structured directory

The pipeline ensures automatic processing of videos placed inside ./test_videos/.

📊 Performance Considerations

GPU acceleration supported

CPU fallback available

Offline inference compatible

Modular structure allows model swapping

🏭 Industrial Suitability

Fully offline inference

No cloud dependency

Scalable to surveillance or monitoring systems

Easily extendable to additional object categories

Modular retraining possible
