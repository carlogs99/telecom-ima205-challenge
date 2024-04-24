ssh login@gpuX.enst.fr
cd /home/infres/login

Install conda:
Choose a version: https://repo.anaconda.com/archive/
Copy the link to the version you need.

cd /tmp
curl -O https://repo.anaconda.com/archive/Anaconda3-2024.02-1-Linux-x86_64.sh
sha256sum Anaconda3-2024.02-1-Linux-x86_64.sh
bash Anaconda3-2024.02-1-Linux-x86_64.sh
cd /home/infres/login/anaconda3
source activate

check installation
conda list
conda init

reset connection (CTRL-D and connect again by ssh)

create a conda environment:
conda create --name cuda_test
conda activate cuda_test
conda install -c anaconda cudatoolkit -y
conda install pytorch-cuda=12.1 -c pytorch -c nvidia -y
conda install pytorch torchvision -c pytorch -c nvidia -y

select GPU:
check usage doing nvidia-smi
export CUDA_VISIBLE_DEVICES=X
echo $CUDA_VISIBLE_DEVICES 