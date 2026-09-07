# 🚀 AI & Deep Learning Practice Projects

이 저장소는 시계열 데이터 예측 및 이미지 패턴 분류를 위한 딥러닝(Deep Learning) 실습 프로젝트 모음입니다. Google Colab 환경에서 진행되었으며, 데이터 전처리부터 모델 구축, 학습, 시각화까지의 전체 파이프라인을 다룹니다.

---

## 📂 Projects Summary

### 1. 📈 NASA LSTM 시계열 예측 (NASA_lstm_실습.ipynb)
* **주제**: 시계열 데이터를 활용한 상태 예측 및 잔여 수명(RUL) 추정
* **주요 기술**: TensorFlow/Keras, LSTM (Long Short-Term Memory)
* **핵심 내용**:
  * 시계열 데이터의 슬라이딩 윈도우(Sliding Window) 전처리
  * 순환 신경망(LSTM) 레이어를 활용한 장기 의존성 패턴 학습
  * 예측 결과 및 실제값 비교 시각화

### 2. 🔍 반도체 웨이퍼 맵 결함 분류 (Wafer_Map_결함_분류_실습.ipynb)
* **주제**: CNN 기반의 반도체 Wafer Map 결함 패턴 자동 분류
* **주요 기술**: TensorFlow/Keras, CNN (Convolutional Neural Network)
* **핵심 내용**:
  * `ImageDataGenerator`를 활용한 픽셀 정규화 ($0 \sim 1$) 및 데이터 분할
  * `Conv2D` + `MaxPooling2D` 레이어를 통한 공간 특징 추출
  * 9개 결함 클래스 분류 (`Softmax`) 및 예측 결과(`Pred` vs `True`) 시각화

---

## 🛠️ Environment & Tools
* **Language**: Python 3.x
* **Framework**: TensorFlow, Keras
* **Libraries**: NumPy, Pandas, Matplotlib
* **Environment**: Google Colab
