# Image Classification
Deep Learning for Image Classification with EM Algorithms

## 1. 관리자 권한으로 Anaconda prompt 띄움
 ``` anaconda
conda update -n base -c defaults conda
```
-> 아나콘다 업데이트

## 2.가상환경 만들기

작업 폴더 만들기
 ``` anaconda
mkdir dl_project2 
```
접근
 ``` anaconda
cd dl_project2
```


conda create -n vir_project2(가상환경이름) python=3.8
 ``` anaconda
conda create -n vir_project2 python=3.8
```
 ``` anaconda
conda env list <-가상환경보기
 ```
  ``` anaconda
conda env remove --n 가상환경이름  <-가상환경 삭제
```

## 3. 가상환경 접근
conda activate vir_project2
(가상환경 나오기 conda deactivate)

## 4. 주피터 노트북 설치
conda install -n vir_project2 ipython notebook jupyter
## 5. 텐서플로 설치
conda install -n vir_project2 tensorflow-gpu==2.6.0 -y
(-y 는 proceed ([y]/n)에서 y로 전부 해주기)

## 6.커널 등록
python -m ipykernel install --user --name ai_project2

## 7.커널 삭제
jupyter kernelspec uninstall 커널이름

## 본인은 gpu가 보이지 않는 문제 발생
시스템 환경변수 편집
https://cho000023.tistory.com/74
#cuda 버전바꾸기
https://tw0226.tistory.com/79?category=872393
