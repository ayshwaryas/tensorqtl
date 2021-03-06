### Setup CUDA drivers and TensorFlow on GCP

Launch a new instance configured with Ubuntu 16.04 LTS and a GPU, clone this repository, and run the following:
#### Install CUDA
```bash
sudo ./install_cuda.sh
sudo reboot
# verify
nvidia-smi
nvcc --version
```

#### Install Python 3
```bash
sudo apt update
sudo apt install -y python3-pip python3-dev python-virtualenv
pip3 install --upgrade virtualenv
virtualenv venv
source venv/bin/activate
pip3 install -r requirements.txt
# verify
python -c "import tensorflow as tf; print(tf.__version__)"
```

#### Install rmate (optional)
```bash
sudo apt install -y ruby
mkdir ~/bin
curl -Lo ~/bin/rmate https://raw.githubusercontent.com/textmate/rmate/master/bin/rmate
chmod a+x ~/bin/rmate
echo 'export RMATE_PORT=${rmate_port}' >> ~/.bashrc
```
