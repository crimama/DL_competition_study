# 3회차 - 베이스라인 띠벨롭 
# 미션 
- 2회차까지 진행하며 기본적인 베이스라인을 구축 했습니다. 
- 성능과는 별개로 최소한 model.fit이 돌아가고 submission이 가능한 수준으로 코드를 작성했습니다. (혹시 submission이 안되셨다면....!)
- 그래서 이번 회차에서는 베이스라인을 디벨롭 하고자 합니다. 
- 새로운 모델을 설계하고, 성능을 향상시키기 보다는 조금 더 수월하게 베이스라인을 실행시키기 위한 회차라고 생각하시면 좋을 것 같습니다. 




## 1단계 - 데이터 제너레이터 (혹은 데이터 로더)
- 앞선 회차 까지는 이미지를 메모리에 모두 한번에 로드 한 뒤 학습을 진행 했습니다. train_x.shape = (3000,256,256,3) 대략 이런 형태의 데이터가 얻어집니다. 
- 하지만 이렇게 하다 보니 램이 감당을 못합니다. 램에 어떻게 올렸다 하더라도 GPU memory에서 터질게 분명합니다. 
- 그렇기 때문에 데이터를 한번에 메모리에 올리지 않고 Mini Batch 사이즈 만큼 메모리에 올리고 학습에 사용하고 버리고 다시 로드하는 방식을 사용해야 합니다. 
- 이렇게 할 수 있도록 해주는 것이 데이터 제너레이터, 내지 데이터 로더 입니다. 
- 이미지 디렉토리만 넣으면 바로 만들어 주는 모듈이 존재하기는 하지만 이는 이미지와 디렉토리를 해당 모듈에 맞춰야 하는 문제가 있습니다. 
- 그래서 대부분은 커스텀 데이터 제너레이터를 만듭니다. 
- 이번 스텝에서 할 것이 바로 커스텀 데이터 제너레이터 만들기 입니다. 
- **이 부분은 직접 찾아서 하기 보다는 코드를 보면서 하나씩 익히기를 추천 드립니다**
- **To do** 
  - 커스텀 데이터 제너레이터 만들기 
  - `from tensorflow.keras.utils import Sequence` 사용 
- 
  
## 2단계 - 전이 학습 
- 앞선 회차까지는 Convolution을 이용해 직접 레이어를 구성했습니다. 
- 하지만 대부분의 경우 직접 레이어를 구성해서 짜는 경우는 없으며 Pretrained Network를 가져와 Feature extraction을 Fine-tuning하는 경우가 대부분입니다. 
- Transfer learning이란 미리 대용량 데이터로 학습된 모델을 가져온 뒤 자신의 데이터로 추가 학습시키는 방법을 뜻 합니다. 
- 이번 스텝에서는 ResNet 또는 EfficientNet을 이용해 Transfer Learning을 하고자 합니다. 
- **To do** 
  - ResNet 이나 EfficientNet 가져오기 
  - `from tensorflow.keras.applications import EfficientNetB0,ResNet50` 사용 
  - 

## 3단계 - Functional API 
- 케라스를 이용해 모델을 구성하는 방법에는 크게 2가지가 존재합니다. 
  - Sequence 
  - Functional
- Sequence는 객체 하나에 model을 선언해준 뒤 레이어를 하나씩 쌓는 형태입니다. 
- Functional은 여러 객체를 활용해서 파이써닉 하게 모델을 만드는 방식입니다. 
- 처음엔 Sequence가 편하지만 복잡한 모델을 만드는 것에 한계가 있기 때문에 Functional 형태를 사용하는 것이 좋습니다. 
- **To do**
  - functional 방식 익히기  


## 4단계(Option) : Iferenece하여 제출하기 
- Test이미지를 읽어와서 제출하기 

# 참고 
[class3_baseline.ipynb](Baseline/class3_Baseline.ipynb) [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/crimama/DL_competition_study/blob/main/Baseline/class3_Baseline.ipynb)
