# Pose Estimation on Qualcomm® Hexagon™

### About Advantech Container Catalog
The **Advantech Container Catalog** delivers hardware-accelerated AI containers pre-integrated for seamless edge deployment. These containers abstract complexities like SDK setup, runtime compatibility, and toolchain dependencies—offering rapid development pathways for platforms such as the **Qualcomm® QCS6490** SoC.

### Key benefits of the Container Catalog include:
| Feature / Benefit             | Description                                                                     |
| ----------------------------- | ------------------------------------------------------------------------------- |
| Optimized for Pose Estimation | Full stack for real-time human pose detection using YOLOv8 and HRNet            |
| Dual Export Workflows         | Supports both Qualcomm® AI Hub and Ultralytics-based model conversion pipelines |
| DSP & GPU Acceleration        | Utilizes Hexagon™ DSP 770 and Adreno™ 643 GPU for low-latency inference         |
| Multiple Runtime Support      | Integrated support for QNN, SNPE, and LiteRT runtimes                           |
| Format Flexibility            | Compatible with `.tflite`, `.dlc`, and `.so` models                             |
| Real-Time Vision Pipeline     | GStreamer-based multimedia framework with OpenCV integration                    |
| Fully Scripted Deployment     | Includes automated scripts for model export, quantization, and benchmarking     |
| ROS Integration               | Compatible with Qualcomm Robotics Reference Distro with ROS 1.3-ver.1.1         |
| Versatile Use Cases           | Tailored for fitness, sports analytics, AR/VR, healthcare, and robotics         |

## Container Overview

**Pose Estimation on Qualcomm® Hexagon™** is a comprehensive container solution for running real-time pose estimation models on the **QCS6490** platform. With **full DSP acceleration**, this container supports inference with models such as **YOLOv8-Pose** and **HRNet**, optimized for low-latency applications in the edge environment.

This container offers:

* **Dual Pose Estimation Workflows**:

  * **Ultralytics Export**: Use YOLOv8-native tools to export to TFLite for fast iteration and prototyping
  * **AI Hub Conversion**: Import optimized HRNet models from Qualcomm’s Hugging Face repository for deployment-ready performance

* **Integrated Runtime Stack**:

  * Pre-installed support for **QNN**, **SNPE**, and **LiteRT**
  * Includes **GStreamer**, **OpenCV**, and **Python 3.10** for full pipeline development

* **Hardware-Accelerated Inference**:

  * INT8 inference on **Hexagon™ DSP 770**
  * FP32 fallback and GPU acceleration via **Adreno™ 643 GPU**

* **Multi-Model Format Compatibility**:

  * Native support for `.tflite`, `.dlc`, and `.so` formats across supported runtimes

* **Preconfigured Scripts & Utilities**:

  * `advantech-coe-model-export.sh` and `advantech-aihub-model-export.sh` for exporting pose estimation models
  * `wise-bench.sh` for validating AI environment and runtime compatibility

* **Ready for Edge AI Use Cases**:

  * Tailored for robotics, fitness tracking, motion capture, smart surveillance, AR/VR, and more
  * Optimized for deployment on **Advantech AOM-2721** with **QCS6490 SoC**

* **Seamless ROS Support**:

  * Plug-and-play compatibility with **Qualcomm Robotics Reference Distro (ROS 1.3-ver.1.1)** for robotic applications

## Container Demo
![Demo](%2Fdata%2Fgifs%2Fqc-yolo-pose-demo.gif)

## Use Cases

1. **Fitness & Rehabilitation**

    - Real-time exercise feedback: AI observe and correct posture during workouts for form optimization and injury prevention.
    - Physical therapy training: Monitor patient movement and progression during rehab, enabling remote guidance.

2. **Sports Analytics**

    - Performance analysis: Track athlete movements to analyze techniques, optimize form, and reduce injury risks.

3. **Animation, AR/VR & Gaming**

    - Markerless motion capture: Drive character animations and virtual avatars using live body pose data from cameras.
    - Immersive gameplay: Enable gesture-based controls for a more engaging experience.

4. **Healthcare & Assisted Living**

    - Postural monitoring: Detect poor ergonomics or risky body alignment in real time—useful for workplaces or elder care.
    - Fall detection: Identify and respond to falls or sudden movements in assisted living scenarios.

5. **Surveillance & Behavior Analysis**

    - Abnormal activity detection: Analyze body postures and gestures to flag suspicious behavior or loose safety compliance.

6. **Human–Robot Interaction**

    - Gesture-driven control: Robots interpret user pose for intuitive interactions, like teleoperation or cooperative tasks.

7. **Retail & AR Applications**

    - Virtual try-ons: Use pose detection to enhance virtual fitting rooms—simulate apparel on users in real time.
    - Interaction tracking: Monitor customer postures and gestures to improve retail UX.

8. **Human–Computer Interaction & Gesture Recognition**

    - Touchless interfaces: Enable users to control systems or express intent using body pose or gestures (e.g., in sign language applications).

## Key Features

- **Complete AI Framework Stack:** QNN SDK (QNN, SNPE), LiteRT

- **Edge AI Capabilities:** Optimized pipelines for real-time vision tasks (pose estimation)

- **Preconfigured Environment:** Comes with all necessary tools pre-installed in a container

- **Full DSP/GPU Acceleration:** Utilize Qualcomm® Hexagon™ DSP and Adreno™ GPU for fast and efficient inference

- **Dual Pose Estimation Workflows:** Support for both Qualcomm® AI Hub conversion and Ultralytics export methods, enabling better flexibility

## Host Device Prerequisites

| Component       | Specification      |
|-----------------|--------------------|
| Target Hardware | [Advantech AOM-2721](https://www.advantech.com/en/products/a9f9c02c-f4d2-4bb8-9527-51fbd402deea/aom-2721/mod_f2ab9bc8-c96e-4ced-9648-7fce99a0e24a) |
| SoC             | [Qualcomm® QCS6490](https://www.advantech.com/en/products/risc_evaluation_kit/aom-dk2721/mod_0e561ece-295c-4039-a545-68f8ded469a8)   |
| GPU             | Adreno™ 643        |
| DSP             | Hexagon™ 770       |
| Memory          | 8GB LPDDR5         |
| Host OS         | QCOM Robotics Reference Distro with ROS 1.3-ver.1.1       |


## Container Environment Overview

### Software Components on Container Image

| Component   | Version | Description                                                                                  |
|-------------|---------|----------------------------------------------------------------------------------------------|
| LiteRT      | 1.3.0   | Provides QNN TFLite Delegate support for GPU and DSP acceleration                            |
| [SNPE](https://docs.qualcomm.com/bundle/publicresource/topics/80-70014-15B/snpe.html)        | 2.29.0  | Qualcomm’s Snapdragon Neural Processing Engine; optimized runtime for Snapdragon DSP/HTP     |
| [QNN](https://docs.qualcomm.com/bundle/publicresource/topics/80-63442-50/introduction.html)         | 2.29.0  | Qualcomm® Neural Network (QNN) runtime for executing quantized neural networks                |
| GStreamer   | 1.20.7  | Multimedia framework for building flexible audio/video pipelines                             |
| Python   | 3.10.12  | Python runtime for building applications                             |
| OpenCV    | 4.11.0 | Computer vision library for image and video processing |


### Container Quick Start Guide
For container quick start, including the docker-compose file and more, please refer to [README.](https://github.com/Advantech-EdgeSync-Containers/Pose-Estimation-on-Qualcomm-Hexagon/blob/main/README.md)

### Supported AI Capabilities

#### Vision Models

| Model                               | Format       | Note                                                                 |
|-------------------------------------|--------------|----------------------------------------------------------------------|
| YOLOv8 Detection                    | TFLite INT8  | Downloaded from Ultralytics` official source and exported to TFLite using Ultralytics Python packages |
| YOLOv8 Segmentation                 | TFLite INT8  | Downloaded from Ultralytics` official source and exported to TFLite using Ultralytics Python packages |
| YOLOv8 Pose Estimation              | TFLite INT8  | Downloaded from Ultralytics` official source and exported to TFLite using Ultralytics Python packages |
| Lightweight Face Detector           | TFLite INT8  | Converted using Qualcomm® AI Hub                                       |
| FaceMap 3D Morphable Model          | TFLite INT8  | Converted using Qualcomm® AI Hub                                       |
| DeepLabV3+ (MobileNet)              | TFLite INT8  | Converted using Qualcomm® AI Hub                                       |
| DeepLabV3 (ResNet50)                | SNPE DLC TFLite | Converted using Qualcomm® AI Hub                                       |
| HRNet Pose Estimation (INT8)        | TFLite INT8  | Converted using Qualcomm® AI Hub                                       |
| PoseNet (MobileNet V1)              | TFLite       | Converted using Qualcomm® AI Hub                                       |
| MiDaS Depth Estimation              | TFLite INT8  | Converted using Qualcomm® AI Hub                                       |
| MobileNet V2 (Quantized)            | TFLite INT8  | Converted using Qualcomm® AI Hub                                       |
| Inception V3 (SNPE DLC)             | SNPE DLC TFLite | Converted using Qualcomm® AI Hub                                       |
| YAMNet (Audio Classification)       | TFLite       | Converted using Qualcomm® AI Hub                                       |
| YOLO (Quantized)                    | TFLite INT8  | Converted using Qualcomm® AI Hub                                       |

### Language Models Recommendation

| Model                               | Format       |   Note                                                         |
|-------------------------------------|--------------|----------------------------------------------------------------|
| Phi2                                | .so          | Converted using Qualcomm's LLM Notebook for Phi-2              |
| Tinyllama                           | .so          | Converted using Qualcomm's LLM Notebook for Tinyllama          |
| Meta Llama 3.2 1B                   | .so          | Converted using Qualcomm's LLM Notebook for Meta Llama 3.2 1B  |                                   |

## Supported AI Model Formats

| Runtime | Format  | Compatible Versions | 
|---------|---------|---------------------|
| QNN     | .so     |       2.29.0        |
| SNPE    | .dlc    |       2.29.0        |
| LiteRT  | .tflite |       1.3.0         | 

## Hardware Acceleration Support

| Accelerator | Support Level | Compatible Libraries |
|-------------|---------------|----------------------|
| GPU         |  FP32         | QNN, SNPE, LiteRT    |             
| DSP         |  INT8         | QNN, SNPE, LiteRT    |   

## Best Practices

* Prefer **INT8 quantized** models for DSP acceleration
* Ensure **fixed batch sizes** when converting models
* Use lower `GST_DEBUG` levels for stable multimedia handling
* Always validate exported models on-device after deployment