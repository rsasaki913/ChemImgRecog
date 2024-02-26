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

Assume the structure of directories is the following:

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
      YOLOv8n.pt
      YOLOv8x.pt
    ChemImgRecog.yaml
```

*Replace uppercase letters with lowercase letters (Images→images, Labels→labels).

#### Evaluation
For validation data:
```bash
yolo task=detect mode=val model=./weights/~.pth data=ChemImgRecog.yaml
```
For test data:
```bash
yolo task=detect mode=val model=./weights/~.pth data=ChemImgRecog.yaml split=test
```
#### Predict images
```bash
yolo task=detect mode=predict model=./weights/~.pth source=path/*.jpg
```
Rewritten path to the directory containing the images.

## <div align="center">Action Recognition</div>
See and download the [3D ResNets Repo]([https://github.com/ultralytics/ultralytics](https://github.com/kenshohara/3D-ResNets-PyTorch)).

<details open>
<summary>Preperation</summary>

Pip install the required packages; Python3, PyTorch, FFmpeg, FFprobe

Assume the structure of directories is the following:

```misc
~/
  3D-ResNets-PyTorch-master/
    data/
      sample_videos/
        jpg/
          AddingReagent/
            Adding_sample/
          Stirring/
            Stirring_sample/
          Transferring/
            Transferring_sample/
        video/
        test.json
        Classes.names
      results/
        save_3218.pth
        opts.json
    datasets/
    models/
    util_scripts/
    main.py
    the other files
```
