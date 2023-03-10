# PUGAN-pytorch
Pytorch unofficial implementation of PUGAN (a Point Cloud Upsampling Adversarial Network, ICCV, 2019)

From https://github.com/UncleMEDM/PUGAN-pytorch

#### Install some packages

RTX 3070; Python 3.6; Pytorch 1.7.0; CUDA 11.1.

simply by 
```
conda create -n pugan python=3.6

conda activate pugan

conda install pytorch==1.7.0 torchvision torchaudio cudatoolkit=11.0 -c pytorch

pip install -r requirements.txt
```
#### Install Pointnet2 module
```
cd pointnet2
python setup.py install
```
#### Install KNN_cuda
```
pip install --upgrade https://github.com/unlimblue/KNN_CUDA/releases/download/0.2/KNN_CUDA-0.2-py3-none-any.whl
```
#### dataset
We use the PU-Net dataset for training, you can refer to https://github.com/yulequan/PU-Net to download the .h5 dataset file, which can be directly used in this project.
#### modify some setting in the option/train_option.py
change opt['project_dir'] to where this project is located, and change opt['dataset_dir'] to where you store the dataset.
<br/>
also change params['train_split'] and params['test_split'] to where you save the train/test split txt files.
#### training
```
cd train
python train.py --exp_name=the_project_name --gpu=gpu_number --use_gan --batch_size=12
```

