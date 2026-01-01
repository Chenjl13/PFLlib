# PFLlib – Learning & Reproduction Notes

This repository is forked from [TsingZ0/PFLlib](https://github.com/TsingZ0/PFLlib).

## Purpose of this Fork
- Record my learning process of Federated Learning
- Reproduce baseline experiments (FedAvg on MNIST)
- Document environment setup and common pitfalls

## First Successful Run: FedAvg on MNIST
### Clone down
- git clone https://github.com/TsingZ0/PFLlib
### Open Terminal window, move into powershell
- wsl
### Go back to user catalog
- cd
### Install miniconda
- wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
- bash Miniconda3-latest-Linux-x86_64.sh
- cd /mnt/c/Users/Admin/Desktop/PFllib-master/PFllib-master

### Set Tsinghua Source
- mkdir -p ~/.pip 
- cat > ~/.pip/pip.conf << 'EOF' 
- [global] 
- index-url = https://pypi.tuna.tsinghua.edu.cn/simple 
- timeout = 120 
- EOF

### Config
- chmod +x prepare.sh
- conda env create -f env_cuda_latest.yaml
- source ~/.bashrc
- conda activate pfllib

### Test Environment1
- python -V
- python - << 'EOF'
- import torch
- print("torch:", torch.__version__)
- print("cuda available:", torch.cuda.is_available())
- EOF

### Test Environment2
- python - << 'EOF'
- import system
- print("PFLlib core imported successfully")
- EOF

### Run
- cd system
- export LD_LIBRARY_PATH=/usr/lib/wsl/lib:$LD_LIBRARY_PATH
- python main.py -data MNIST -m CNN -algo FedAvg -gr 20 -did 0





