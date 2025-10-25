# UniGS-Viewer

[Video](https://www.bilibili.com/video/BV1EdYyzbEXj/)

[Deploy Video](https://www.bilibili.com/video/BV1bhspzZEcW/?vd_source=0211af3bb655d5627b96e8718e3af59f)

Available in Linux with Cmake.

Example data [Google Drive](https://drive.google.com/file/d/1zaFeOR_kUm9oajyBhc67Dj7ScfJRYe2S/view?usp=drive_link)

## Step 1
```
# git clone

git clone https://github.com/xieyuser/SIBR_multimodal_viewer.git

cd SIBR_multimodal_viewer

mkdir build && cd build

```

## Step 2
```
# conda virtual environment
conda create -n $CONDA_ENV_NAME$ python=3.9

conda activate $CONDA_ENV_NAME$

mamba install --file ../conda_pkgs.txt  pytorch=2.0.0=cuda112py39ha9981d0_200 -c nvidia -c conda-forge -c pytorch

mamba install opencv=4.5.3

mamba install cxx-compiler=1.5.2

mamba install cmake=3.26.4 make

# verify
which gcc

>> gcc path should be in conda environment

e.g. /home/xieys/miniforge3/envs/viewer/bin/gcc
```

## Step 3
```
# build

cmake .. -DCMAKE_INSTALL_PREFIX=${CONDA_ENV_NAME}

e.g. cmake .. -DCMAKE_INSTALL_PREFIX=/home/xieys/miniforge3/envs/viewer

make -j16

make install
```

## Step 4
```
# run
/home/xieys/projects/SIBR_multimodal_viewer/install/bin/SIBR_gaussianViewer_app -m $

e.g. /home/xieys/projects/SIBR_multimodal_viewer/install/bin/SIBR_gaussianViewer_app -m ~/doc/garden

```
