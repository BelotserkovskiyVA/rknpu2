# RKNPU2
## onnx2rknn convert

# I) Docker instruction
## 1. Install Docker
Please install Docker according to the official manual:
https://docs.docker.com/install/linux/docker-ce/ubuntu/
## 2. docker pull
```
docker pull belotserkovskiyva/rknn_toolkit2_py38:1.4.0
```
## 3. Run image
Execute the following command to run the docker image. After running, it will enter the bash
environment.
```
docker run -t -i --privileged -v /dev/bus/usb:/dev/bus/usb <IMAGE_ID> /bin/bash
```
## 4. Run demo (ONNX2RKNN convert)
```
cd /examples/onnx/yolov5/
python3 test.py
```
# II) Git instruction
install the RKNN-Toolkit2 to convert the model. (https://wiki.t-firefly.com/en/ROC-RK3568-PC/usage_npu.html)

## 1. Install virtualenv、Python3.8 and pip3
```
sudo apt install virtualenv 
sudo apt-get install python3 python3-dev python3-pip
```
## 2. Install dependent libraries
```
sudo apt-get update
sudo apt-get install libxslt1-dev zlib1g zlib1g-dev libglib2.0-0 libsm6 \
libgl1-mesa-glx libprotobuf-dev gcc
```
## 3. Use virtualenv and install Python dependency, such as requirements_cp38-1.4.0.txt
```
virtualenv -p /usr/bin/python3 venv
source venv/bin/activate
#python3 -m pip install --upgrade pip
cd rknn-toolkit2/
pip3 install -r doc/requirements_cp38-*.txt
```
## 3. If conda activate
```
virtualenv -p /opt/conda/bin/python3 venv
source venv/bin/activate
#python3 -m pip install --upgrade pip
cd rknn-toolkit2/
pip3 install -r doc/requirements_cp38-*.txt
```
## 4.Install RKNN-Toolkit2，such as rknn_toolkit2-1.4.0_22dcfef4-cp38-cp38-linux_x86_64.whl
```
sudo pip3 install packages/rknn_toolkit2*cp38*.whl
```
## 5. Check if RKNN-Toolkit2 is installed successfully or not，press key ctrl+d to exit
(venv) user@linuxx:~/rknn-toolkit2$ python3
from rknn.api import RKNN

# ONNX2RKNN convert
then use onnx2rknn.py (rknpu2/onnx2rknn.py)

#to run inference
see:
-> rknpu2/examples/rknn_yolov5_demo/
