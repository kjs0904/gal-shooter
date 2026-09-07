# 🛠️ NASA Jet Engine RUL(잔여 수명) 예측 AI 모델

NASA C-MAPSS 센서 시계열 데이터를 활용하여 제트 엔진의 잔여 수명(Remaining Useful Life)을 예측하는 LSTM 기반 예지보전(Predictive Maintenance) 프로젝트입니다.

## 📌 주요 기능 및 특징
- **시계열 데이터 처리**: 30 타임스텝의 Sliding Window 기법을 활용한 3D Tensor 변환
- **스케일링**: MinMaxScaler를 적용하여 24개 센서 변수 정규화
- **딥러닝 아키텍처**: Keras 기반 LSTM 회귀(Regression) 모델 구현
- **자산화**: 학습된 모델(.keras) 및 스케일러(.pkl) 저장을 통한 추론 파이프라인 탑재

## 📂 파일 구조
- `NASA_lstm_실습.ipynb` : 데이터 전처리, 모델 학습 및 평가 전체 코드
- `my_rul_lstm_model.keras` : 학습 완료된 LSTM 모델 가중치
- `my_scaler.pkl` : 데이터 전처리에 사용된 Scaler

## 🚀 실행 및 추론 방법 (Inference)
```python
import tensorflow as tf
import joblib

# 모델 및 스케일러 로드
model = tf.keras.models.load_model('my_rul_lstm_model.keras')
scaler = joblib.load('my_scaler.pkl')

# 3D 입력 데이터(1, 30, 24) 전처리 후 예측
predicted_rul = model.predict(input_tensor)
