
# Error & Solution
## AttributeError: type object 'h5py.h5.H5PYConfig' has no attribute '__reduce_cython__'

h5py install 하지 않아 오류 발생 
```anaconda
pip install --upgrade h5py
```


# ------------------------------------------------------------------------------


## ImportError: cannot import name 'LayerNormalization' from 'tensorflow.python.keras.layers.normalization' (C:\Users\tmdwh\.conda\envs\vir_project2\lib\site-packages\tensorflow\python\keras\layers\normalization\__init__.py)

```anaconda
pip uninstall -y tensorflow keras tf-nightly keras-nightly
pip install tensorflow==2.6.0
```


# ------------------------------------------------------------------------------


```python
from tensorflow import keras
from tensorflow.keras import datasets
cifar10 = datasets.cifar10 
```
## ->cannot import name 'dtensor' from 'tensorflow.compat.v2.experimental'

```anaconda
pip install keras
```



```anaconda
pip install keras==2.6.* -i https://pypi.douban.com/simple/
```

# ------------------------------------------------------------------------------


## 정규화
## 오류 cannot import name 'to_categorical' from 'keras.utils'
from keras.utils import to_categorical

(edit)
```python
from tensorflow.keras.utils import to_categorical
```

# ------------------------------------------------------------------------------


# 참고사이트 
https://www.cnblogs.com/Sofiacodes/p/16295957.html
https://hdevstudy.tistory.com/116


