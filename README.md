# Research on Detection Technology of Underwater Pipeline in Sonar Image

水下管线声纳图像检测技术研究

## Env

```sh
# 创建虚拟环境
python3 -m venv .venv
source .venv/bin/activate

# update pip
pip list
pip install --upgrade pip

# install
pip install -r requirement.txt
```

## Jupyter Lab

- jupyter/src/main.ipynb: 基本流程
- jupyter/src/numpy-basic.ipynb: numpy快速入门及基本使用
- jupyter/src/histogram.ipynb: 直方图相关内容
- jupyter/src/thresholding.ipynb: 阈值分割相关内容
- jupyter/src/filter.ipynb: 滤波相关内容
- jupyter/src/morphological.ipynb: 形态学相关内容
- jupyter/src/edge-detection.ipynb: 边缘检测相关内容

### 本地运行

```sh
jupyter lab
```

## Web

- 这个项目的网站
- ~~参考~~ 抄的: <https://www.uav-hirap.org/>
- 正在建设中


### 本地运行

```sh
flask --app web init-db
python manage.py runserver
# visit http://127.0.0.1:5000/
```

## YOLO

### yolov5

- [yolov5.ipynb](yolo/yolov5.ipynb)

- 使用预训练的yolov5s模型, 先试试原始图像, emm, 一个都没检测出来
```
detect: weights=['yolov5s.pt'], source=data/images, data=data/coco128.yaml, imgsz=[640, 640], conf_thres=0.25, iou_thres=0.45, max_det=1000, device=, view_img=False, save_txt=False, save_csv=False, save_conf=False, save_crop=False, nosave=False, classes=None, agnostic_nms=False, augment=False, visualize=False, update=False, project=runs/detect, name=exp, exist_ok=False, line_thickness=3, hide_labels=False, hide_conf=False, half=False, dnn=False, vid_stride=1
YOLOv5 🚀 v7.0-226-gdd9e338 Python-3.10.12 torch-2.0.1+cu118 CUDA:0 (Tesla T4, 15102MiB)

Fusing layers... 
YOLOv5s summary: 213 layers, 7225885 parameters, 0 gradients
image 1/10 /content/yolov5/data/images/181.bmp: 160x640 (no detections), 43.0ms
image 2/10 /content/yolov5/data/images/20.bmp: 416x640 (no detections), 43.1ms
image 3/10 /content/yolov5/data/images/21.bmp: 640x448 (no detections), 42.4ms
image 4/10 /content/yolov5/data/images/22.bmp: 640x640 (no detections), 12.3ms
image 5/10 /content/yolov5/data/images/24.bmp: 640x352 (no detections), 55.1ms
image 6/10 /content/yolov5/data/images/28.bmp: 640x384 (no detections), 45.5ms
image 7/10 /content/yolov5/data/images/29.bmp: 640x448 (no detections), 8.9ms
image 8/10 /content/yolov5/data/images/30.bmp: 640x576 (no detections), 44.0ms
```

- 换用处理后的图像, 同时还上传了两张其他图片, 看看效果
```
detect: weights=['yolov5s.pt'], source=data/images, data=data/coco128.yaml, imgsz=[640, 640], conf_thres=0.25, iou_thres=0.45, max_det=1000, device=, view_img=False, save_txt=False, save_csv=False, save_conf=False, save_crop=False, nosave=False, classes=None, agnostic_nms=False, augment=False, visualize=False, update=False, project=runs/detect, name=exp, exist_ok=False, line_thickness=3, hide_labels=False, hide_conf=False, half=False, dnn=False, vid_stride=1
YOLOv5 🚀 v7.0-226-gdd9e338 Python-3.10.12 torch-2.0.1+cu118 CUDA:0 (Tesla T4, 15102MiB)

Fusing layers... 
YOLOv5s summary: 213 layers, 7225885 parameters, 0 gradients
image 1/20 /content/yolov5/data/images/1.png: 448x640 (no detections), 43.8ms
image 2/20 /content/yolov5/data/images/181.bmp: 160x640 (no detections), 43.7ms
image 3/20 /content/yolov5/data/images/2.png: 640x448 (no detections), 48.2ms
image 4/20 /content/yolov5/data/images/20.bmp: 416x640 (no detections), 44.7ms
image 5/20 /content/yolov5/data/images/21.bmp: 640x448 (no detections), 9.8ms
image 6/20 /content/yolov5/data/images/22.bmp: 640x640 (no detections), 12.3ms
image 7/20 /content/yolov5/data/images/24.bmp: 640x352 (no detections), 41.6ms
image 8/20 /content/yolov5/data/images/28.bmp: 640x384 (no detections), 45.3ms
image 9/20 /content/yolov5/data/images/29.bmp: 640x448 (no detections), 8.9ms
image 10/20 /content/yolov5/data/images/3.png: 640x640 (no detections), 12.4ms
image 11/20 /content/yolov5/data/images/30.bmp: 640x576 (no detections), 46.4ms
image 12/20 /content/yolov5/data/images/4.png: 640x352 (no detections), 7.9ms
image 13/20 /content/yolov5/data/images/5.png: 640x384 (no detections), 8.1ms
image 14/20 /content/yolov5/data/images/6.png: 640x448 (no detections), 8.9ms
image 15/20 /content/yolov5/data/images/7.png: 640x544 (no detections), 44.3ms
image 16/20 /content/yolov5/data/images/8.png: 224x640 (no detections), 44.3ms
image 17/20 /content/yolov5/data/images/bus.jpg: 640x480 4 persons, 1 bus, 44.4ms
image 18/20 /content/yolov5/data/images/newbing.jpg: 640x544 1 traffic light, 1 clock, 11.8ms
image 19/20 /content/yolov5/data/images/test.jpg: 384x640 1 frisbee, 1 kite, 42.8ms
```
- 还是没有检测出来, 话说 clock 是什么鬼啊, 有点离谱. 还有frisbee, 明明是月亮...

### yolov8

- [YOLOv8_Tutorial.ipynb](yolo/YOLOv8_Tutorial.ipynb)

- 先用 yolov8n.pt 模型试试有没有变化
```
Ultralytics YOLOv8.0.196 🚀 Python-3.10.12 torch-2.0.1+cu118 CUDA:0 (Tesla T4, 15102MiB)
YOLOv8n summary (fused): 168 layers, 3151904 parameters, 0 gradients, 8.7 GFLOPs

image 1/1 /content/1.png: 448x640 (no detections), 99.6ms
Speed: 3.7ms preprocess, 99.6ms inference, 26.9ms postprocess per image at shape (1, 3, 448, 640)
Results saved to runs/detect/predict2
💡 Learn more at https://docs.ultralytics.com/modes/predict
Ultralytics YOLOv8.0.196 🚀 Python-3.10.12 torch-2.0.1+cu118 CUDA:0 (Tesla T4, 15102MiB)
YOLOv8n summary (fused): 168 layers, 3151904 parameters, 0 gradients, 8.7 GFLOPs

image 1/1 /content/3.png: 640x640 (no detections), 8.6ms
Speed: 4.8ms preprocess, 8.6ms inference, 21.1ms postprocess per image at shape (1, 3, 640, 640)
Results saved to runs/detect/predict3
💡 Learn more at https://docs.ultralytics.com/modes/predict
Ultralytics YOLOv8.0.196 🚀 Python-3.10.12 torch-2.0.1+cu118 CUDA:0 (Tesla T4, 15102MiB)
YOLOv8n summary (fused): 168 layers, 3151904 parameters, 0 gradients, 8.7 GFLOPs

image 1/1 /content/20.bmp: 416x640 (no detections), 96.6ms
Speed: 3.2ms preprocess, 96.6ms inference, 27.5ms postprocess per image at shape (1, 3, 416, 640)
Results saved to runs/detect/predict4
💡 Learn more at https://docs.ultralytics.com/modes/predict
Ultralytics YOLOv8.0.196 🚀 Python-3.10.12 torch-2.0.1+cu118 CUDA:0 (Tesla T4, 15102MiB)
YOLOv8n summary (fused): 168 layers, 3151904 parameters, 0 gradients, 8.7 GFLOPs

image 1/1 /content/newbing.jpg: 640x544 1 clock, 102.1ms
Speed: 4.3ms preprocess, 102.1ms inference, 84.2ms postprocess per image at shape (1, 3, 640, 544)
Results saved to runs/detect/predict5
💡 Learn more at https://docs.ultralytics.com/modes/predict
```
- 依旧没有检测出来, 不过 traffic light 没检测出来, 算是提高了准确度?
- 应该是模型的问题, 找了一个用输电线数据集训练的yolo模型 [yolov8_wires_dect_best.pt](yolo/model/yolov8_wires_dect_best.pt) (都是线性目标, ~~问题不是很大~~)
- 分别识别了原始图像和处理后图像, 奇怪的是, 原始图像都识别出来了, 但是处理后图像只识别了一个 (还是模型的问题?)
- yolo识别结果: /yolo
- **已弃坑**

## Reference

- [海底管线检测](https://www.google.com/search?q=%E6%B5%B7%E5%BA%95%E7%AE%A1%E7%BA%BF%E6%A3%80%E6%B5%8B)
    - [水下管线目标的探测方法与优缺点分析](https://www.f-sea.com/newsinfo/606322.html)
    - [声学探测技术在海底石油管线铺设后调查中的应用](http://qdhys.ijournal.cn/html/hykx/2021/7/20210712.html)
- [CFAR](https://www.google.com/search?q=CFAR&sourceid=chrome&ie=UTF-8)
    - [wiki](https://en.wikipedia.org/wiki/Constant_false_alarm_rate)
    - [雷达无线电系列（二）经典CFAR算法图文解析与实现（matlab）](https://www.cnblogs.com/Mufasa/p/10900334.html)
    - [Google](https://www.google.com/search?q=Constant+false+alarm+rate&sourceid=chrome&ie=UTF-8)
- [2D-CA-CFAR](https://www.google.com/search?q=%E4%BA%8C%E7%BB%B4%E5%B9%B3%E5%9D%87%E6%81%92%E8%99%9A%E8%AD%A6%E7%AE%97%E6%B3%95)
    - [2D-CA-CFAR](https://www.mathworks.com/help/phased/ref/2dcfardetector.html)
- [Gabor滤波](https://www.google.com/search?q=Gabor%E6%BB%A4%E6%B3%A2)
    - <https://zhuanlan.zhihu.com/p/33311267>
    - <https://xuewenyuan.github.io/posts/2016/05/blog-post-1/>
    - [详解Gabor Filter](https://www.jianshu.com/p/a6d6f344609f)
    - [matlab](https://www.mathworks.com/help/images/ref/imgaborfilt_zh_CN.html)
    - <https://cloud.tencent.com/developer/article/1052377>
    - <https://juejin.cn/post/6977932255109283877>
- [Dennis Gabor](https://en.wikipedia.org/wiki/Dennis_Gabor)
    - [Gabor filter](https://en.wikipedia.org/wiki/Gabor_filter)

- [OpenCV](https://github.com/opencv/opencv)
- [numpy](https://numpy.org/)
- [pillow](https://python-pillow.org/)
- [Jupyter](https://jupyter.org/)
- [flask](https://github.com/pallets/flask)
    - <https://flask.palletsprojects.com/en/2.3.x/>
- [yolo](https://colab.research.google.com/github/ultralytics/yolov3/blob/master/tutorial.ipynb)
- [yolov8 github](https://github.com/ultralytics/ultralytics)
- [yolov8 tutorial](https://colab.research.google.com/github/ultralytics/ultralytics/blob/main/examples/tutorial.ipynb#scrollTo=kUMOQ0OeDBJG)
