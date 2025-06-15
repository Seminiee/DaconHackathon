# 🚗 전기차 가격 예측 프로젝트

<div align="center">

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Pandas](https://img.shields.io/badge/Pandas-1.3+-green.svg)
![XGBoost](https://img.shields.io/badge/XGBoost-1.5+-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

</div>

## 📋 프로젝트 개요

이 프로젝트는 전기차 가격 예측을 위한 데이터 분석 및 모델링을 수행했습니다. 데이터 전처리, 특성 엔지니어링, 모델링의 전체 과정을 구현했으며, 특히 데이터 품질 관리와 특성 처리에 중점을 두었습니다.

## 🛠 기술 스택

<div align="center">

| 카테고리 | 기술 |
|:--------:|:----:|
| **데이터 처리** | Python, Pandas, NumPy |
| **데이터 변환** | Scikit-learn |
| **모델링** | XGBoost |
| **시각화** | Matplotlib |
| **버전 관리** | Git |

</div>

## 🔄 데이터 처리 과정

### 1. 📥 데이터 로드 및 탐색
- train.csv, test.csv 파일 로드
- 데이터 기본 정보 확인
- 결측치 및 이상치 탐색

### 2. 🧹 데이터 전처리
- **결측치 처리**
  - 배터리용량 결측치를 차량상태와 모델별 평균값으로 대체
  - 전역 평균값을 fallback으로 사용하는 안전장치 구현
- **이상치 처리**
  - 주행거리 데이터의 구간화
  - 비즈니스 도메인 지식을 활용한 구간 설정 (5000km, 10000km, 30000km, 80000km, 120000km)

### 3. 🔄 특성 처리
1. **범주형 변수 처리**
   - Label Encoding을 통한 범주형 변수 변환
   - 새로운 카테고리 처리 로직 구현
   ```python
   categorical_features = ['제조사', '모델', '구동방식', '사고이력', '주행거리구간별']
   ```

2. **수치형 변수 처리**
   - 배터리용량 결측치 처리
   - 주행거리 구간화

### 4. ⚙️ 특성 엔지니어링
- 차량상태 및 모델별 평균 배터리용량 계산
- 주행거리 구간화를 통한 새로운 특성 생성
- 불필요한 특성 제거 및 최적화

### 5. 🤖 모델링
- XGBoost 모델 구현
- 하이퍼파라미터 최적화
- 모델 학습 및 예측

## 📊 데이터 품질 관리 전략

### 1. 결측치 처리
- 도메인 기반 결측치 대체 전략
- 계층적 평균값 계산 방식 적용

### 2. 이상치 처리
- 시각화를 통한 이상치 탐지
- 비즈니스 규칙 기반 데이터 구간화

### 3. 데이터 검증
- 각 처리 단계별 데이터 검증
- 최종 데이터셋 품질 확인

## 🏆 프로젝트 성과
- ✅ 효율적인 데이터 전처리 및 특성 엔지니어링
- ✅ 기본적인 결측치 및 이상치 처리 구현
- ✅ XGBoost를 활용한 예측 모델 구축

## 🔮 향후 개선 사항

### 1. 데이터 품질 관리 전략 구현
- [ ] 데이터 검증 단계 추가
- [ ] 데이터 품질 모니터링 시스템 구축
- [ ] 자동화된 데이터 품질 검증 프로세스 구현

### 2. 데이터 파이프라인 자동화
- [ ] Airflow/Dagster를 활용한 파이프라인 자동화
- [ ] 데이터 품질 모니터링 시스템 구축

### 3. 데이터 버전 관리
- [ ] DVC를 활용한 데이터 버전 관리
- [ ] 실험 추적 시스템 구축

### 4. 성능 최적화
- [ ] 대용량 데이터 처리 최적화
- [ ] 분산 처리 시스템 도입 검토

## 📁 프로젝트 구조
```
.
├── data/
│   ├── train.csv
│   ├── test.csv
│   └── sample_submission.csv
├── dacon_electric_car_price_prediction_submission_code.ipynb
├── my_submission_final.csv
└── README.md
```

---

<div align="center">

### 📝 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

</div>