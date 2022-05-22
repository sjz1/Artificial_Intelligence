# Image Classification Preferences
Deep Learning for Image Classification with EM Algorithms

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

## 본인은 gpu가 보이지 않는 문제 발생
### GPU사용 여부 확인
 ``` anaconda
 nvidia-smi
 ```
 -> GPU가 사용되지 않는 것을 확인
 -> CUDA version은 현재 버전이 아닌 권장 버전
 

시스템 환경변수 편집
https://cho000023.tistory.com/74
#cuda 버전바꾸기
https://tw0226.tistory.com/79?category=872393


