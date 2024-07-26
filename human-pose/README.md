This repo contains some experiments with DensePose estimation

### How to run

1\. Download COCO images
```
mkdir -p data/coco && cd data/coco
wget http://images.cocodataset.org/zips/train2014.zip
wget http://images.cocodataset.org/zips/val2014.zip
unzip train2014.zip
unzip val2014.zip
rm train2014.zip val2014.zip
cd ../..

```
2\. Download DensePose annotations
```
mkdir -p data/densepose && cd data/densepose
wget https://dl.fbaipublicfiles.com/densepose/densepose_coco_2014_train.json
wget https://dl.fbaipublicfiles.com/densepose/densepose_coco_2014_valminusminival.json
wget https://dl.fbaipublicfiles.com/densepose/densepose_coco_2014_minival.json
wget https://dl.fbaipublicfiles.com/densepose/densepose_coco_2014_test.json
cd ../..
```

3\. If you want to run training, you should also download some evaluation data
```
mkdir -p data/densepose/eval_data && cd data/densepose/eval_data 
wget https://dl.fbaipublicfiles.com/densepose/densepose_eval_data.tar.gz
tar xvf densepose_eval_data.tar.gz
rm densepose_eval_data.tar.gz
cd ../../..
```

4\. Next, you should install the libraries
```
pip install -r requirements.txt
```

5\. Finally you can start training by running:
```
python run_trainer.py --experiments_dir=my-experiments
```

