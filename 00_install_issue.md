| 수정일자 |
|:---:|
| 19.11.09 |


### Tensorflow 2.0 설치시 발생한 이슈

##### 설치는 간단 (anaconda 가상환경에서 설치)

```
1. conda create -n 가상환경명 python=3.6
2. conda activate 가상환경명
3. conda install -c anaconda tensorflow-gpu
```

##### 하지만, 설치이후 아래의 에러 발생
`UnknownError : Failed to get convolution algorithm. This is probably because cuDNN failed to initialize, so try looking to see if a warning log message was printed above.`

##### cudatoolkit과 cudnn의 버전호환 이슈인거 같은데 원론적인 해결은 못한 상태.
##### 일시적인 해결책으로 다음 코드를 가장 상단에 default로 적고 시작 (적어도 에러는 안남.)
```
from tensorflow.compat.v1 import ConfigProto
from tensorflow.compat.v1 import InteractiveSession

config = ConfigProto()
config.gpu_options.allow_growth = True

InteractiveSession(config=config) # 이게 핵심.
```
