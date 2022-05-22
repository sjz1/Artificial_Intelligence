# Image Classification Preferences
Deep Learning for Image Classification with EM Algorithms


## 0. nvidia 드라이버 및  cuda toolkit (회원가입필요)설치하기
https://www.nvidia.com/download/index.aspx?lang=en-us

https://developer.nvidia.com/cuda-toolkit-archive


## 1. anaconda version update
관리자 권한으로 Anaconda prompt 띄움
 ``` anaconda
conda update -n base -c defaults conda
```
-> 아나콘다 업데이트

## 2.가상환경 만들기

작업 폴더 만들기
 ``` anaconda
mkdir dl_project2 
```
만든 작업 폴더에 접근
 ``` anaconda
cd dl_project2
```

가상환경을 만들어줌
conda create -n vir_project2(가상환경이름) python=3.8
 ``` anaconda
conda create -n vir_project2 python=3.8
```
가상환경보기
 ``` anaconda
conda env list
 ```
가상환경 삭제
  ``` anaconda
conda env remove --n 가상환경이름  
```
![가상환경](https://user-images.githubusercontent.com/68888169/169697197-6441d43e-e823-4352-a631-bca457943447.png)


## 3. 가상환경 접근
 ``` anaconda
conda activate vir_project2
 ```
(가상환경 나오기)
 ``` anaconda
conda deactivate
 ```

## 4. 주피터 노트북 설치
 ``` anaconda
conda install -n vir_project2 ipython notebook jupyter
 ```
## 5. 텐서플로 설치
 ``` anaconda
conda install -n vir_project2 tensorflow-gpu==2.6.0 -y
 ```
(-y 는 proceed ([y]/n)에서 y로 전부 해주기)

## 6.커널 등록
 ``` anaconda
python -m ipykernel install --user --name ai_project2
 ```
 //커널 삭제//
 ``` anaconda
jupyter kernelspec uninstall 커널이름
 ```

## 7. 커널을 사용하여서 jupyter notebook을 연 다음 
 ``` python
import tensorflow as tf
 ```
  ``` python
from tensorflow.python.client import device_lib
 ```
  ``` python
print(device_lib.list_local_devices())
 ```

## 본인은 gpu가 보이지 않는 문제 발생

오류내용(버전이 맞지 않음)

W tensorflow/core/common_runtime/gpu/gpu_device.cc:1835] Cannot dlopen some GPU libraries.

Please make sure the missing libraries mentioned above are installed properly if you would like to use GPU. 

Follow the guide at https://www.tensorflow.org/install/gpu for how to download and setup the required libraries for your platform.


### GPU사용 여부 확인
 ``` anaconda
 nvidia-smi
 ```
 ![GPU사용x](https://user-images.githubusercontent.com/68888169/169697358-c8cc1a9e-beb6-44b2-9250-4c9a0d82c2a7.png)
 

 -> GPU가 사용되지 않는 것을 확인     
 
 -> CUDA version은 현재 버전이 아닌 권장 버전
 
 cuda 와 tensorflow version 확인
 
 ![쿠다버전확인](https://user-images.githubusercontent.com/68888169/169698104-65e50697-df58-4cad-94f2-f6d3bda536f3.png)
 
 conda activate 가상환경이름
 
  ``` anaconda
 conda activate vir_project2
 ```
 
 
 아래 코드를 conda에 tensorflow 2.6.0 version 인지 확인
 
 ``` anaconda
conda list
```

![tensorflow_버전확인](https://user-images.githubusercontent.com/68888169/169697959-88a38919-ef9e-4eea-8bd3-a08d445d80e6.png)
 
 tensorflow-gpu가 2.6.0이 아닌 것을 확인
 
 ![gpu호환](https://user-images.githubusercontent.com/68888169/169698057-29001df9-9eb1-408b-bfa9-08005f5b8008.png)

필자는 cuda 버전을 11.2를 사용하므로

위의 표에 따라 tensorflow-gpu 를 2.6.0으로 바꿔줌

tensorflow-gpu다운로드
 ``` anaconda
conda install tensorflow==2.6.0
```

본인은 혹시 몰라서 pip 에도 다운로드 받음(pip와 conda랑은 다르다 pip는 지양하기)
 ``` anaconda
pip install tensorflow==2.6.0
```


오류내용

I tensorflow/core/platform/cpu_feature_guard.cc:142] This TensorFlow binary is optimized with oneAPI Deep Neural Network Library (oneDNN) to use the following CPU instructions in performance-critical operations:  AVX AVX2
To enable them in other operations, rebuild TensorFlow with the appropriate compiler flags.
W tensorflow/stream_executor/platform/default/dso_loader.cc:64] Could not load dynamic library 'cudnn64_8.dll'; dlerror: cudnn64_8.dll not found


2022-05-21 03:17:50.532733: W tensorflow/core/common_runtime/gpu/gpu_device.cc:1835] Cannot dlopen some GPU libraries. Please make sure the missing libraries mentioned above are installed properly if you would like to use GPU. Follow the guide at https://www.tensorflow.org/install/gpu for how to download and setup the required libraries for your platform.
Skipping registering GPU devices...
[name: "/device:CPU:0"
device_type: "CPU"
memory_limit: 268435456
locality {
}
incarnation: 16477647163233809568

cudnn을 cuda파일에 덮어쓰기를 안해서 문제가 발생

CUDA -> v11.2 -> lib,include,bin 파일을 덮어쓰기

위에 표에 따라 cuDNN 8.1 version 다운받아서 덮어씀


### 다운로드 링크
https://developer.nvidia.com/rdp/cudnn-archive

(C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2)

//cuDNN 버전 안 맞으면 나오는 오류문구//
Could not load dynamic library 'cudnn64_8.dll'; dlerror: cudnn64_8.dll not found


### 확인해보기
 ``` python
import tensorflow as tf
from tensorflow.python.client import device_lib
print(device_lib.list_local_devices())
 ```

## 해결 완료
![image](https://user-images.githubusercontent.com/68888169/169699255-a22e59c7-6ac9-463e-9456-1919ee0f3443.png)


## 8 가상환경에 추가적인 라이브러리 설치
``` anaconda
conda install -n vir_project2 numpy
conda install -n vir_project2 scipy
conda install -n vir_project2 matplotlib spyder pandas scikit-learn -y
```

## 9 파이토치 설치

링크

https://pytorch.org/

https://pytorch.org/get-started/previous-versions/

확인

cudatoolkit 11.2 가 없어서 11.0으로 다운그레이드 하여서 다운
``` anaconda
conda install pytorch torchvision torchaudio cudatoolkit=11.0 -c pytorch
```

주피터 노트북을 켜고
### pytorch 잘 깔렸는지 확인

``` python
import torch
torch.cuda.is_avaviable()
```
false 나와서 cuda 11.1로 다시 진행

https://pytorch.org/get-started/previous-versions/
``` anaconda
pip install torch==1.9.1+cu111 torchvision==0.10.1+cu111 torchaudio==0.9.1 -f https://download.pytorch.org/whl/torch_stable.html
```


##### 참고 사이트
###### 시스템 환경변수 편집
https://cho000023.tistory.com/74
###### cuda 버전바꾸기
https://tw0226.tistory.com/79?category=872393
###### cuda nvidia gpu cudnn 버전확인
https://velog.io/@khs0415p/NVIDIA-GPU-CUDA-CUDNN-%EB%B2%84%EC%A0%84-%ED%99%95%EC%9D%B8
##### GPU인식문제
https://aeir.tistory.com/entry/Tensorflow-GPU-%EC%9E%91%EB%8F%99%ED%95%98%EC%A7%80-%EC%95%8A%EC%9D%84%EB%95%8C-%EC%9E%AC%EC%84%A4%EC%B9%98-%EC%97%86%EC%9D%B4-%EC%88%98%EB%A6%AC%ED%95%98%EB%8A%94-%EB%B2%95?category=896072?category=896072
##### cuDNN 버전 문제
https://electrondiy.tistory.com/m/108
