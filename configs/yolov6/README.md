# YOLOv6

> [YOLOv6: A Single-Stage Object Detection Framework for Industrial Applications](https://arxiv.org/abs/2209.02976)

<!-- [ALGORITHM] -->

## Abstract

For years, YOLO series have been de facto industry-level standard for efficient object detection. The YOLO community has prospered overwhelmingly to enrich its use in a multitude of hardware platforms and abundant scenarios. In this technical report, we strive to push its limits to the next level, stepping forward with an unwavering mindset for industry application. Considering the diverse requirements for speed and accuracy in the real environment, we extensively examine the up-to-date object detection advancements either from industry or academy. Specifically, we heavily assimilate ideas from recent network design, training strategies, testing techniques, quantization and optimization methods. On top of this, we integrate our thoughts and practice to build a suite of deployment-ready networks at various scales to accommodate diversified use cases. With the generous permission of YOLO authors, we name it YOLOv6. We also express our warm welcome to users and contributors for further enhancement. For a glimpse of performance, our YOLOv6-N hits 35.9% AP on COCO dataset at a throughput of 1234 FPS on an NVIDIA Tesla T4 GPU. YOLOv6-S strikes 43.5% AP at 495 FPS, outperforming other mainstream detectors at the same scale (YOLOv5-S, YOLOX-S and PPYOLOE-S). Our quantized version of YOLOv6-S even brings a new state-of-the-art 43.3% AP at 869 FPS. Furthermore, YOLOv6-M/L also achieves better accuracy performance (i.e., 49.5%/52.3%) than other detectors with the similar inference speed. We carefully conducted experiments to validate the effectiveness of each component.

<div align=center>
<img src="https://github.com/meituan/YOLOv6/raw/main/assets/speed_comparision_v2.png"/>
</div>

## Results and models

### COCO

| Backbone | Arch | size | SyncBN | AMP | Mem (GB) | box AP |                           Config                            |                                                                                                                                                           Download                                                                                                                                                           |
| :------: | :--: | :--: | :----: | :-: | :------: | :----: | :---------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| YOLOv6-n |  P5  | 640  |  Yes   | Yes |   6.04   |  36.2  | [config](../yolov6/yolov6_n_syncbn_fast_8xb32-400e_coco.py) | [model](https://download.openmmlab.com/mmyolo/v0/yolov6/yolov6_n_syncbn_fast_8xb32-400e_coco/yolov6_n_syncbn_fast_8xb32-400e_coco_20221030_202726-d99b2e82.pth) \| [log](https://download.openmmlab.com/mmyolo/v0/yolov6/yolov6_n_syncbn_fast_8xb32-400e_coco/yolov6_n_syncbn_fast_8xb32-400e_coco_20221030_202726.log.json) |
| YOLOv6-t |  P5  | 640  |  Yes   | Yes |   8.13   |  41.0  | [config](../yolov6/yolov6_t_syncbn_fast_8xb32-400e_coco.py) | [model](https://download.openmmlab.com/mmyolo/v0/yolov6/yolov6_t_syncbn_fast_8xb32-400e_coco/yolov6_t_syncbn_fast_8xb32-400e_coco_20221030_143755-cf0d278f.pth) \| [log](https://download.openmmlab.com/mmyolo/v0/yolov6/yolov6_t_syncbn_fast_8xb32-400e_coco/yolov6_t_syncbn_fast_8xb32-400e_coco_20221030_143755.log.json) |
| YOLOv6-s |  P5  | 640  |  Yes   | Yes |   8.88   |  44.0  | [config](../yolov6/yolov6_s_syncbn_fast_8xb32-400e_coco.py) | [model](https://download.openmmlab.com/mmyolo/v0/yolov6/yolov6_s_syncbn_fast_8xb32-400e_coco/yolov6_s_syncbn_fast_8xb32-400e_coco_20221102_203035-932e1d91.pth) \| [log](https://download.openmmlab.com/mmyolo/v0/yolov6/yolov6_s_syncbn_fast_8xb32-400e_coco/yolov6_s_syncbn_fast_8xb32-400e_coco_20221102_203035.log.json) |

**Note**:

1. The performance is unstable and may fluctuate by about 0.3 mAP.
2. YOLOv6-m,l,x will be supported in later version.
3. If users need the weight of 300 epoch, they can train according to the configs of 300 epoch provided by us, or convert the official weight according to the [converter script](../../tools/model_converters/).

## Citation

```latex
@article{li2022yolov6,
  title={YOLOv6: A Single-Stage Object Detection Framework for Industrial Applications},
  author={Li, Chuyi and Li, Lulu and Jiang, Hongliang and Weng, Kaiheng and Geng, Yifei and Li, Liang and Ke, Zaidan and Li, Qingyuan and Cheng, Meng and Nie, Weiqiang and others},
  journal={arXiv preprint arXiv:2209.02976},
  year={2022}
}
```
