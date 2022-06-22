The part of dataset in here https://drive.google.com/drive/folders/1cZEUnyF3jn0UnQNrhlZCkVjb54XzRTBd?hl=zh-CN
Note that this code is heavily borrowed from RandLA-Net (https://github.com/QingyongHu/RandLA-Net).

### (1) Setup
This code has been tested with Python 3.5, Tensorflow 1.15, CUDA 10.0 and cuDNN 7.4.1 on Ubuntu 16.04.

- Setup python environment
```
conda create -n randlanet python=3.5
source activate randlanet
pip install -r helper_requirements.txt
sh compile_op.sh
```

### (2) BF
`/data/BF`.

- Preparing the dataset:
```
python utils/data_prepare_BF.py
```
- Start 6-fold cross validation:
```
sh jobs_6_fold_cv_bf.sh
```
- Move all the generated results (*.ply) in `/test` folder to `/data/BF/results`, calculate the final mean IoU results:
```
python utils/6_fold_cv.py
```
### Citation
If you find our work useful in your research, please consider citing:

@article{su2022dla,
	  title={DLA-Net: Learning dual local attention features for semantic segmentation of large-scale building facade point clouds},
	  author={Yanfei Su and Weiquan Liu and Zhimin Yuan and Ming Cheng and Zhihong Zhang and Xuelun Shen and Cheng Wang},
	  journal={Pattern Recognition},
                  volume = {123},
                  pages = {108372},
	          year = {2022},
                  issn = {0031-3203},
                  doi = {https://doi.org/10.1016/j.patcog.2021.108372},
                  url = {https://www.sciencedirect.com/science/article/pii/S0031320321005525},
}

