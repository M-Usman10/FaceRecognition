 1-First you need to download anaconda by running following commands:

wget -O anaconda.sh https://repo.anaconda.com/archive/Anaconda2-5.3.0-Linux-x86_64.sh

chmod a+x anaconda.sh

source ./anaconda.sh

echo 'export PATH=~/anaconda2/bin:$PATH'>> ~./bashrc

source ~/.bashrc

2-Download and install Cuda and CUDNN using following commands:

curl -O https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_9.0.176-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu1604_9.0.176-1_amd64.deb
sudo apt-get update
sudo apt-get install cuda-9-0
sudo nvidia-smi -pm 1
echo "Downloading and installing CUDNN"
wget -O cudnn1.deb https://www.dropbox.com/s/jhbiqxo7vwcczpr/libcudnn7_7.3.1.20-1%2Bcuda9.0_amd64.deb?dl=0
sudo dpkg -i cudnn1.deb
wget -O cudnn2.deb https://www.dropbox.com/s/cmbmloxmbjdxgiy/libcudnn7-dev_7.3.1.20-1%2Bcuda9.0_amd64.deb?dl=0
sudo dpkg -i cudnn2.deb
wget -O cudnn3.deb https://www.dropbox.com/s/a3iwf7ko4x70yuw/test.deb?dl=0
sudo dpkg -i cudnn3.deb
echo 'export CUDA_HOME=/usr/local/cuda' >> ~/.bashrc
echo 'export PATH=$PATH:$CUDA_HOME/bin' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=/usr/local/cuda/extras/CUPTI/lib64:$LD_LIBRARY_PATH' >> ~/.bashrc
source ~/.bashrc


3-Install tensorflow for gpu
sudo apt-get install python-dev python-pip libcupti-dev
sudo pip install tensorflow-gpu


Model is already trained but you can retrain it with different parameters. Preprocessing.ipynb prepares the data, Training.ipynb trains and save model to disk and then testing.ipynb validates and test the model.

Note: Download and extract your data into this folder with name directory name 'Images' if you want to run preprocesing.ipynb again.
