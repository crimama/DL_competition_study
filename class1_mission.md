# 1회차 - 기본 베이스라인 구축 
- colab or kaggle 환경에서 진행 


# 미션 
- 이번 1회차 미션의 목적은 저번 스터디의 기억을 되살려 보는 것입니다. 
- 저번 회차에서는 Tabular 데이터, 수치 데이터 위주로 진행이 되었습니다. 
- 하지만 이번 스터디에서 다루는 대회는 이미지 데이터이기 때문에 이 이미지 데이터와 친숙해지고자 합니다. 

## 1단계 - 데이터 디렉토리 로드 
- 데이터 다운로드 후 코랩에 업로드 : 구글 드라이브 마운트 or gdown, or 직접 업로드 
- 데이터 가져와서 unzip 
- 이미지들의 디렉토리 읽어오기 : glob or os 사용 
- 읽어 온 이미지 디렉토리들 중 하나 이미지로 로드한 후 시각화 하기 : CV2, plt.imshow 사용

## 2단계 - 이미지 데이터 로드 및 전처리 
- 1단계에서 이미지 디렉토리를 읽어 왔으니 이제 이미지 데이터를 직접 로드 해야 합니다. 
  - 빈 리스트 변수 생성 
  - 저장한 이미지 디렉토리들로 부터 디렉토리 하나씩 불러와 이미지 로드하는 for문 작성 
  - 이미지 로드 후 앞서 생성한 빈 리스트에 append 
  - for 문 다 돌아간 뒤 이미지가 들어있는 리스트 변수를 numpy로 변환 
- 데이터 전처리 
  - 이미지의 사이즈를 변경 및 통일 : cv2 사용 
  - 이미지들 정규화 진행 
  - (optional) 이미지들 데이터 타입 float16으로 변경 


## 3단계 - 라벨 데이터 전처리 
- 해당 Task 는 Supervised Classification이므로 Y에 해당하는 라벨 데이터가 필요합니다. 

  1.train_csv 읽어오기 : 판다스


  2.train_csv 에서 label 정보만 따로 가져와서 변수에 저장 : 판다스, 넘파이 


  3.2번에서 만든 변수에서 np.unique로 한개씩만 뽑아서 다른 변수에 저장 : np.unique

  4. np.unique로 만든 변수를 이용해 아티스트의 이름을 숫자로 변환 해주는 dict 형태의 label encoder 생성 

## 4단계 - Train-valid 분리 


# 참고 자료 
[class1_baseline.ipynb](Baseline/class1_Baseline.ipynb) [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/crimama/DL_competition_study/blob/main/Baseline/class1_Baseline.ipynb)
