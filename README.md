# 🚀 Industrial AI & Manufacturing Data Science Portfolio

반도체/제조 공정 데이터 분석 및 품질/이상 탐지 모델 구현을 위한 학습 및 실습 포트폴리오 저장소입니다.  
공정 시계열 예측부터 웨이퍼 결함 이미지 분류, 제조 시계열/비전 센서 기반 이상치 탐지(Anomaly Detection)까지 다양한 머신러닝/딥러닝 기법을 실습하고 현업 응용 가능성을 탐구합니다.

---

## 🛠 주요 프로젝트 및 실습 내용

### 1. 🏭 반도체 웨이퍼 맵 결함 분류 (Wafer Map Defect Classification)
- **주요 내용**: 이미지 기반 웨이퍼 결함 패턴(Ring, Edge, Spot 등)을 분류하기 위한 CNN 파이프라인 구축
- **기술 스택**: Python, TensorFlow/Keras, CNN, `ImageDataGenerator`
- **핵심 특징**: 
  - 대용량 웨이퍼 이미지 데이터의 효율적인 메모리 로딩 및 전처리
  - 합성곱(Convolution) 및 풀링(Pooling) 계층을 활용한 자동 특징 추출
  - 실제 반도체 제조 데이터셋(WM811K) 연동 및 수율 향상 목적의 수시/정기 감시 시스템 응용 고려

---

### 2. 🔍 제조 공정 데이터 이상치 탐지 (Anomaly Detection)

#### 🌲 Isolation Forest 기반 이상 탐지 (`Isolation_Forest_실습.ipynb`)
- **알고리즘 원리**: 데이터 공간을 무작위로 분할하여, 정상 군집에 비해 분할 횟수가 적은(트리 깊이가 짧은) 고립된 데이터를 이상치로 판별
- **기술 스택**: Python, Scikit-learn (`IsolationForest`), Matplotlib
- **핵심 성과**:
  - `decision_function` 기반 이상치 점수 계산 및 2차원 산점도 상 점 크기/색상 시각화
  - 개별 의사결정나무(Decision Tree) 분기 구조 시각화를 통한 알고리즘 동작 메커니즘 검증
  - 원본 데이터(Ground Truth)와 모델 예측 결과의 1:1 비교 그래프 구현

#### 🎯 One-Class SVM 기반 이상 탐지 (`One_Class_SVM_실습.ipynb`)
- **알고리즘 원리**: 정상 데이터만을 학습하여 데이터 공간 상의 최적 결정 경계(Hyperplane/Boundary)를 형성하고, 경계 밖의 데이터를 이상치로 분류
- **기술 스택**: Python, Scikit-learn (`OneClassSVM`), Matplotlib
- **핵심 성과**:
  - 정상 데이터 단독 학습(Unsupervised/Semi-supervised setting)을 통한 경계선 창출
  - 격자(Grid Mesh) 데이터를 활용한 Decision Boundary 선 시각화 및 밀도 차이 채색
  - 정상 품질 데이터 확보가 용이하고 불량 데이터가 극히 적은 실제 제조 현장 적용성 확인

---

### 3. 📈 NASA 센서 시계열 데이터 수명 예측 (LSTM)
- **주요 내용**: 항공 엔진 및 설비 센서 시계열 데이터를 활용한 잔여 수명(RUL) 예측
- **기술 스택**: Python, TensorFlow/Keras, LSTM
- **핵심 특징**: 시간적 흐름과 연속적 데이터 패턴을 반영한 예지보전(Predictive Maintenance) 모델 구축

---

## 💻 개발 환경 및 워크플로우

- **Development**: Google Colab (GPU)
- **Storage & Backup**: Google Drive
- **Version Control**: GitHub (`kjs0904/gal-shooter`)

---

## 🔮 향후 개선 및 확장 계획 (Future Work)

1. **WM811K 데이터셋 기반 실무형 모듈 확장**:
   - 클래스 불균형(Class Imbalance) 대응을 위한 Loss 조정 및 Augmentation 기법 적용
   - 모델 판단 근거 시각화를 위한 **Grad-CAM** 도입
2. **이상 탐지 알고리즘 현업화 적용**:
   - FDC(Facility Data Collection) 설비 센서 데이터 결합 및 실시간 이상 탐지 파이프라인 구축
