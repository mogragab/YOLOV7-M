# Official YOLOv7-M

## Installation
``` shell
git clone https://github.com/ultralytics/yolov5  # clone
cd yolov7-m
pip install -r requirements.txt
```

##  Dataset
[Data Link Roboflow](https://universe.roboflow.com/yolo-sxtmz/teeth-gzkv1/dataset/12)


```python
!pip install roboflow

from roboflow import Roboflow
rf = Roboflow(api_key="IzDI0ZkIKq8oBAFQ7Tgl")
project = rf.workspace("yolo-sxtmz").project("teeth-gzkv1")
version = project.version(12)
dataset = version.download("yolov7")

```


## Training

```
python train.py --workers 1 --device 0 --batch-size 32 --data dataset/data.yaml --img 640 640 --weights 'yolov7-x.pt' --name yolov7-m-teeth

```

## Inference
``` shell
python detect.py --weights yolov7-m.pt --conf 0.25 --img-size 640 --source image.jpg
```