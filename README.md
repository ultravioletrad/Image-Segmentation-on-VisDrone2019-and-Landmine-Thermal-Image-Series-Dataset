# UNET Segmentation: VisDrone2019 → Zero‑Shot Transfer to IEEE Landmine Thermal Images

**Model trained exclusively on RGB aerial drone data (VisDrone2019).**  
**Successfully segmented IEEE Landmine Thermal Image Series without any thermal training data.**

This repository documents the training of a custom UNET architecture and the key experimental finding: the model generalizes across sensing modalities —
from visible spectrum aerial imagery to thermal humanitarian landmine detection.

## Key Result: Zero‑Shot Thermal Transfer

- **Training data:** VisDrone2019 (RGB aerial images, drone footage)  
- **Test data:** IEEE Landmine Thermal Image Series (thermal imaging, completely unseen during training)  
- **Finding:** The UNET model successfully segments thermal signatures of landmines despite never seeing thermal data. This suggests that features learned from RGB aerial scenes are robust enough to transfer to a different sensor modality — with direct implications for real‑world humanitarian demining operations.

## 🔬 Why This Matters

| Aspect | Significance |
|--------|--------------|
| **Scientific** | Demonstrates domain transfer from RGB to thermal for segmentation tasks |
| **Humanitarian** | Enables landmine detection in thermal imagery without expensive thermal training sets |
| **Practical** | Opens the door to using existing drone models for new sensing modalities |

## 🚀 Production Deployment
Most notebooks never ship. This model did.
The model was quantized to **TensorFlow Lite** and deployed in a full‑stack production application alongside **YOLOv11 (PyTorch)** for video object detection.

👉 **Live demo:** [ImageSegment AI on Hugging Face Spaces](https://huggingface.co/spaces/imagesegmentsupport/imagesegment-ai)

**Tech stack:** Django REST · React · TFLite (UNET) · YOLOv11 (PyTorch) · PostgreSQL · Cloudinary · Docker

## 📁 Repository Contents

- `ObjectDetection-VisDrone2019 2.ipynb` – Training notebook for the UNET model
- Additional evaluation scripts (if any)

## 📚 Datasets

- **VisDrone2019** – Aerial drone imagery  
"""
https://github.com/VisDrone/VisDrone-Dataset
Citation:
@ARTICLE{9573394,
  author={Zhu, Pengfei and Wen, Longyin and Du, Dawei and Bian, Xiao and Fan, Heng and Hu, Qinghua and Ling, Haibin},
  journal={IEEE Transactions on Pattern Analysis and Machine Intelligence}, 
  title={Detection and Tracking Meet Drones Challenge}, 
  year={2021},
  volume={},
  number={},
  pages={1-1},
  doi={10.1109/TPAMI.2021.3119563}}
"""
"""
VisDromes2019 is a large-scale benchmark dataset with carefully annotated ground-truth for various important 
computer vision tasks, named VisDrone, to make vision meet drones. The VisDrone2019 dataset is collected by 
the AISKYEYE team at Lab of Machine Learning and Data Mining , Tianjin University, China. 
The benchmark dataset consists of 288 video clips formed by 261,908 frames and 10,209 static images,
captured by various drone-mounted cameras, covering a wide range of aspects including location(taken from 14 different cities separated by thousands of kilometers in China), 
environment (urban and country), 
objects (pedestrian, vehicles, bicycles, etc.), and 
density (sparse and crowded scenes).
Note that, the dataset was collected using various drone platforms (i.e., drones with different models),
in different scenarios, and under various weather and lighting conditions. 
These frames are manually annotated with more than 2.6 million bounding boxes of targets of frequent interests,
such as pedestrians, cars, bicycles, and tricycles. Some important attributes including scene visibility,
object class and occlusion, are also provided for better data utilization.
"""
#https://github.com/VisDrone/VisDrone2018-DET-toolkit
#Annotation file format
 #<bbox_left>,<bbox_top>,<bbox_width>,<bbox_height>,<score>,<object_category>,<truncation>,<occlusion>

- **IEEE Landmine Thermal Image Series** – Thermal imaging for landmine detection (used only for zero‑shot testing)
https://ieee-dataport.org/open-access/landmine-thermal-image-series files

## 📄 Citation

If you find this work useful for research or humanitarian applications, please cite:

```bibtex
@misc{ahmad2025unet,
  author = {Rumana Ahmad},
  title = {UNET Segmentation: Zero-Shot Transfer from VisDrone2019 to Landmine Thermal Images},
  year = {2025},
  howpublished = {\url{https://github.com/ultravioletrad/Image-Segmentation-on-VisDrone2019-and-Landmine-Thermal-Image-Series-Dataset}}
}
