# YOLOv8 Pose Model Export Script (QCS6490 Compatible)

This script allows you to export **YOLOv8 pose models** into **quantized TFLite format**, optimized for use with the **Qualcomm® QCS6490 AI accelerator (HTP)**.

> **Note:** This script is designed to run **inside the Docker environment** where all dependencies are already pre-installed.

---

## Parameters

- **model**: Name of the YOLOv8 pose model file (choose from the table below).
- **task**: For as `pose`.

---

## Supported YOLOv8 Pose Models

Use the exact model names listed below as input in the script.

|    Model Name     | Description             | Size    | Accuracy    | Inference Speed |
|-------------------|-------------------------|---------|-------------|-----------------|
| `yolov8n-pose.pt` | Nano - smallest, fastest| ~6 MB   | Low         | Fastest         |
| `yolov8s-pose.pt` | Small - lightweight     | ~11 MB  | Medium      | Very Fast       |
| `yolov8m-pose.pt` | Medium - balanced       | ~25 MB  | Good        | Moderate        |
| `yolov8l-pose.pt` | Large - high accuracy   | ~45 MB  | High        | Slower          |

## Export Pose Models

Export any of the above models using:

```bash
cd /workspace
chmod +x advantech-coe-model-export.sh
./advantech-coe-model-export.sh model="yolov8n-pose.pt" task=pose
```
Repeat with other model names like yolov8n-pose.pt, yolov8m-pose.pt, etc., as needed.

## Output

- The script generates a quantized TFLite model.
- Exported models will be saved in the `/workspace/model/` directory.
- Fully compatible with QCS6490 AI accelerator (HTP) via QNN TFLite delegate.

## Summary

| Property         | Value                         |
|------------------|-------------------------------|
| Task Supported   | pose                          |
| Export Format    | quantized TFLite              |
| Target Platform  | Qualcomm® QCS6490              |
| Output Directory | /workspace/model/             |
| Script Path      | /workspace/advantech-coe-model-export.sh     |
