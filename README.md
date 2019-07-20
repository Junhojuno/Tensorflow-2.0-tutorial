# Tensorflow-2.0-tutorial

### Tensorflow 2.0 공식문서의 권장사항.

  - 1) 작은 함수로 코드를 리팩토링하세요.
  
```
  
  텐서플로 1.x의 일반적인 사용 패턴은 "키친 싱크(kitchen sink)" 전략입니다. 먼저 모든 연산을 결합하여 준비한 다음 session.run()을 사용해 선택한 텐서를 평가합니다. 텐서플로 2.0에서는 필요할 때 호출할 수 있는 작은 함수로 코드를 리팩토링(refactoring)해야 합니다. 모든 함수에 tf.function 데코레이터를 적용할 필요는 없습니다. 모델 훈련의 한 단계(step)나 정방향 연산(forward pass) 같은 고수준 연산에만 tf.function 데코레이터를 적용하세요.

```

  - 2) Keras layer와 model을 사용해 변수를 관리하세요.
```

케라스 모델과 층(layer)은 재귀적으로 의존하는 모든 변수를 수집하여 variables와 trainable_variables 속성으로 제공합니다. 따라서 변수를 지역 범위로 관리하기 매우 쉽습니다.

```

- [처음봐서 당황스러운 tensorflow 2.0 문법](https://github.com/Junhojuno/Tensorflow-2.0-tutorial/blob/master/00.new_method_summary.md)
- [Convolutional Neural Network with mnist](https://github.com/Junhojuno/Tensorflow-2.0-tutorial/blob/master/01_CNN_2_0style.ipynb)
- [Neural Style Transfer]()
- [DCGAN with mnist](https://github.com/Junhojuno/Tensorflow-2.0-tutorial/blob/master/DCGAN_mnist.ipynb)
