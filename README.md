# Image Recognition for Chemical Experiments

## <div align="center">Object Detection</div>
See the [YOLOv8 Docs](https://docs.ultralytics.com) and [YOLOv8 Repositry](https://github.com/ultralytics/ultralytics) for more information.

<details open>
<summary>Preperation</summary>

Pip install the ultralytics package including all [requirements](https://github.com/ultralytics/ultralytics/blob/main/requirements.txt) in a [**Python>=3.8**](https://www.python.org/) environment with [**PyTorch>=1.7**](https://pytorch.org/get-started/locally/).

[![PyPI version](https://badge.fury.io/py/ultralytics.svg)](https://badge.fury.io/py/ultralytics) [![Downloads](https://static.pepy.tech/badge/ultralytics)](https://pepy.tech/project/ultralytics)

```bash
pip install ultralytics
```
Create a directory named "datasets" in "ultralytics".

Move "ChemImgRecog.yaml" and "weights" to ultralytics

Download our image dataset, [Annotated Chemical Apparatus Image Dataset](https://data.mendeley.com/datasets/8p2hvgdvpn/1), and move it in "datasets".

</details>

<details open>
<summary>Running</summary>

Assume the structure of data directories is the following:

```misc
~/
  ultralytics/
    datasets/
      Chemical Apparatus Image Dataset/
          Train/
            images*/
            labels*/
          Valid/
          Test/
          Classes.names
    weights/
      YOLOv8n.pth
      YOLOv8x.pth
    ChemImgRecog.yaml
```

*Replace uppercase letters with lowercase letters (Images→images, Labels→labels).

#### Calculate mAPs

```bash
yolo task=detect mode=val model=./weights/~.pth data=ChemImgRecog.yaml
```

```bash
yolo task=detect mode=val model=./weights/~.pth data=ChemImgRecog.yaml split=test
```
#### Predict images


