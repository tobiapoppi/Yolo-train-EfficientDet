# Yolo-train-EfficientDet
The purpose of this repository is training efficientDet model with a custom dataset.
In this specific case I first want to convert a dataset from YOLO format to COCO format.

First create a new conda environment with the .yml file:
`conda create --file effD36.yml`

Activate the env:
`conda activate effD36`

Install with pip the following packages:
`pip install opencv-python==3.4.2.17`

`python main.py -p /data/effD/dataset/yolo_ds_no_bg/train/ --imgf png --inplace`
`python main.py -p /data/effD/dataset/yolo_ds_no_bg/test/ --imgf png --inplace --output instances_val2017.json`

Specify in the `--imgf` parameter your image extension.
The parameter `--inplace` is an option for saving your annotation json file in the `<-p>/../annotations/<--output>` folder.


Train:
`cd Yolo-trainEfficientDet/EfficientDet`
`python train.py --snapshot imagenet --phi 0 --gpu 0 --random-transform --compute-val-loss --freeze-backbone --batch-size 32 --steps 1000 coco /data/effD/dataset/yolo_ds_no_bg/`

!!aggiustare il fatto di mettere annotation nella parent di train e test
sta dando errori su alcune bounding box
