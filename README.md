## Data sources:
Images from (100K Images): http://bdd-data.berkeley.edu/download.html

Labels from (bdd100k_det_20_labels_trainval.zip): https://dl.cv.ethz.ch/bdd100k/data/

Labels transformed to coco format (saved in `data/annotations/`) with official dataset tools: https://github.com/bdd100k/bdd100k



## Run instructions:

1. Put downloaded 100K images into folders:
    - `data/images/train/`
    - `data/images/val/`
    - `data/images/test/`

2. Create directory `data/labels/`
3. Download and extract https://dl.cv.ethz.ch/bdd100k/data/bdd100k_det_20_labels_trainval.zip 
3. Clone https://github.com/bdd100k/bdd100k
4. Run: 
    - `python3 -m bdd100k.label.to_coco -m det -i bdd100k/labels/det_20/det_train.json -o bdd100k/labels/output/det_train.json`
    - `python3 -m bdd100k.label.to_coco -m det -i bdd100k/labels/det_20/det_val.json -o bdd100k/labels/output/det_val.json`
4. Put the new coco-format annotation files into `data/annotations/det_train.json` and `data/annotations/det_val.json`
3. Run `preprocess.ipynb`
4. Run `training.ipynb`
5. Check results in `runs/detect/train\<run number\>/`