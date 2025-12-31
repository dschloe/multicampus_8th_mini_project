<div align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit_Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/Seaborn-4479A1?style=for-the-badge&logo=seaborn&logoColor=white">
  <img src="https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white">
</div>

# 📊 Diabetes Health Indicators Prediction
> CDC의 설문 데이터를 기반으로 생활 습관 및 건강 지표를 통한 당뇨병 발병 위험 예측 프로젝트

---

## 📌 1. Project Overview
- **주제**: 생활 습관(식습관, 운동 등) 및 신체 상태 지표를 활용한 당뇨병 유무 분류
- **데이터셋**: [Kaggle - Diabetes Health Indicators Dataset](https://www.kaggle.com/datasets/mohankrishnathalla/diabetes-health-indicators-dataset)
- **핵심 목표**: 병원 검사 없이도 설문 데이터를 통해 당뇨병 고위험군을 선별할 수 있는 모델 구축

## 📂 2. Data Dictionary (핵심 변수)
제공된 데이터셋의 주요 컬럼 설명입니다.

| 변수명 | 설명 | 값의 의미 |
| :--- | :--- | :--- |
| **Diabetes_binary** | 당뇨 여부 (**Target**) | 0: 음성, 1: 당뇨/전단계 |
| HighBP | 고혈압 여부 | 0: 정상, 1: 고혈압 |
| HighChol | 고콜레스테롤 여부 | 0: 정상, 1: 높음 |
| BMI | 체질량 지수 | 수치형 |
| Smoker | 흡연 여부 | 100개비 이상 흡연 여부 (0/1) |
| Stroke | 뇌졸중 경험 | 0: 없음, 1: 있음 |
| HeartDiseaseorAttack | 심장질환/심근경색 | 0: 없음, 1: 있음 |
| PhysActivity | 신체 활동 | 최근 30일 이내 운동 여부 (0/1) |
| GenHlth | 주관적 건강 상태 | 1(매우 좋음) ~ 5(매우 나쁨) |
| Age | 연령대 | 1(18-24) ~ 13(80세 이상) |
| Income | 소득 수준 | 1(최저) ~ 8(최고) |

## 🔍 3. Problem Definition
- **데이터 특성**: 본 데이터는 직접적인 임상 측정값이 아닌 **설문 응답 기반**의 데이터입니다. 
- **분석 방향**: "어떤 생활 습관이 당뇨병과 가장 강한 상관관계를 가지는가?"를 파악하고, 클래스 불균형(Imbalance) 문제를 해결하는 데 집중했습니다.

## ⚙️ 4. Data Preprocessing
- **클래스 불균형 해소**: SMOTE 오버샘플링 또는 하이퍼파라미터 조정을 통한 데이터 비대칭 해결.
- **범주형 변수 처리**: 연령(Age), 교육(Education) 등 범주형 데이터의 순서적 특성 반영.
- **데이터 스케일링**: BMI 등 연속형 변수의 분포 정규화.

## 📊 5. EDA Insights
- **고혈압/고콜레스테롤**: 당뇨병 환자군에서 고혈압과 고콜레스테롤 동반 비율이 압도적으로 높게 나타남.
- **주관적 건강도(GenHlth)**: 실제 당뇨병 환자일수록 자신의 건강 상태를 '나쁨(4, 5)'으로 평가하는 경향이 큼.
- **경제적 요인**: 소득(Income) 수준이 낮을수록 당뇨병 유병률이 증가하는 경향 확인.

## 🤖 6. Modeling & Evaluation
| Model | Accuracy | Recall | F1-Score | AUC-ROC |
| :--- | :--- | :--- | :--- | :--- |
| Random Forest | 0.85 | 0.70 | 0.74 | 0.88 |
| **XGBoost** | **0.86** | **0.75** | **0.78** | **0.91** |

> **Note**: 의료 선별 도구로서의 성능을 위해 Recall을 최적화하는 임계값(Threshold) 조정을 수행함.

## 🏆 7. Feature Importance
예측 모델에서 영향력이 가장 컸던 지표 순위:
1. **GenHlth** (주관적 건강 상태)
2. **HighBP** (고혈압)
3. **BMI** (체질량지수)
4. **Age** (연령)
![Q-Q Plot](output/qqplot.png)

## 📝 8. Conclusion
- 병원 수치(혈당 등) 없이도 **주관적 건강 상태와 기초 지표(BMI, 혈압)**만으로 당뇨 위험도를 상당히 높은 확률로 예측할 수 있음을 확인했습니다.
- 이 모델은 보건소 등에서 간단한 설문을 통해 정밀 검사가 필요한 대상자를 선별하는 데 활용될 수 있습니다.

# 📝 보고서
- 프로젝트 상세 보고서는 PDF 슬라이드 자료를 참고하여 주세요
- 00 보고서 : [당뇨병 예측 모델링: 통계분석 및 머신러닝 접근](report/프로젝트보고서.pdf)


# 🔗 배지 및 이모지 공식 소스 링크
| 용도 | 사이트 이름 | 링크 |
| :--- | :--- | :--- |
| **배지 생성** | Shields.io | [https://shields.io/](https://shields.io/) |
| **로고/색상 검색** | Simple Icons | [https://simpleicons.org/](https://simpleicons.org/) |
| **이모지 검색** | Emoji Cheat Sheet | [https://github.com/ikatyang/emoji-cheat-sheet](https://github.com/ikatyang/emoji-cheat-sheet) |



