# SLANT_brain_seg
Deep Whole Brain Segmentation Using SLANT Method. It has been implemented as a single Docker

## Quick Start
### get our docker image
sudo docker pull masidocker/spiders:deep_brain_seg_v1_0_0
## run SLANT brain segmentation
export input_dir=/home/input_dir   #you need to specify the directory
wget https://www.dropbox.com/s/v1u219rhxp1zsst/test_volume.nii.gz?dl=0

sudo nvidia-docker run -it --rm -v /home/yuankai/input_dir/:/INPUTS/ -v /home/yuankai/output_dir:/OUTPUTS masidocker/spiders:deep_brain_seg_v1_0_0 /extra/run_deep_brain_seg.sh

# Detailed envrioment setting (If Necessary)

## Testing platform
Ubuntu 16.04
cuda 8.0
Pytorch 0.2
Docker version 1.13.1-cs9
Nvidia-docker version 1.0.1 / 2.0.3
singularity 2.4.2


## install Docker
```
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt-get update
sudo apt-get install docker-ce
```

## install singularity
```
curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
sudo apt-get update
sudo apt-get install -y nvidia-docker2
```

