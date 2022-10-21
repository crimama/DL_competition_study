# 2회차 - 기본 베이스라인 구축:모델링
# 미션 
- 1회차의 미션에서 기본적인 데이터 로드와 전처리를 진행 했습니다. 
- 이번 회차에서는 간단한 모델을 만들어본 뒤 간단하게 학습을 진행할 예정입니다. 


## 1단계 - 시드 고정 
- 모델 학습의 상당 부분은 random seed에 의해 작동 됩니다. 
- 따라서 추후 동일한 성능을 재현하기 위해서는 이 random seed를 고정해둘 필요가 있습니다. 
- 고정해야 하는 random seed 는 다음과 같습니다. 
  - random 
  - numpy 
  - os 
  - tensorflow 
  
## 2단계 - 모델 선언 
- 1회차 스터디때의 기억을 살려 모델을 만들어 봅시다. 
- 이미지는 기본적으로 Convolution 레이어(CNN)를 사용
  - 예시 : layers.Conv2D(filters = 32,kernel_size=3, strides=1,padding='same')
- 모델 구성은 자유, 모델 선언 후 model.fit이 가능하게만 
- 사용 가능 레이어 : Conv2D, BatchNormalization, Dropout, Dense,Attention 등 keras.layers에 속해 있는 모든 것 
- [템플릿 1](https://github.com/dhrim/2022_DL_competition_study/blob/master/material/deep_learning/template_image_data_vanilla_cnn_classification.ipynb)
- [템플릿 2](https://github.com/dhrim/2022_DL_competition_study/blob/master/material/deep_learning/template_image_data_transfer_learning_classification.ipynb)
- 위 링크에서 **모델** 부문 참고 

## 3단계 - 학습 진행 
- 모델을 만들었으니 학습을 진행해야 합니다. 
- optimizer와 loss_function을 선언한 뒤 model.compile
- (Option) : 콜백 함수를 사용하여 학습 도중 상태 확인 or Verbose 사용 


## 4단계(Option) : Iferenece하여 제출하기 
- Test이미지를 읽어와서 제출하기 

# 참고 
[class2_baseline.ipynb](Baseline/class2_Baseline.ipynb) [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/crimama/DL_competition_study/blob/main/Baseline/class2_Baseline.ipynb)
