# Horse vs Human 이미지 분류 모델

## Skills
<img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white"/>&nbsp;
<img src="https://img.shields.io/badge/pandas-150458.svg?style=for-the-badge&logo=pandas&logoColor=white"/>&nbsp;
<img src="https://img.shields.io/badge/numpy-4d77cf.svg?style=for-the-badge&logo=numpy&logoColor=white"/>&nbsp;
<img src="https://img.shields.io/badge/Matplotlib-11557c.svg?style=for-the-badge&logo=Matplotlib&logoColor=white"/>&nbsp;

## 프로젝트 상세
- **진행 기간**: 2024년 9월 5일 ~ 2024년 9월 9일
- **프로젝트 유형**: 팀 프로젝트

## 프로젝트 목표
말과 사람의 이미지를 딥러닝 모델을 통해 효과적으로 분류하여, 이진 이미지 분류를 기반으로 한 에듀테크 환경에서의 활용 가능성을 모색

## 사용한 데이터 셋
- **데이터**: Laurence Moroney 제공의 말과 사람 컬러 CG 이미지 데이터셋
    - 모델 성능 분석을 위해 총 4개의 딥러닝 모델(MobileNetV2, ResNet50, VGGNet16, DenseNet121) 비교

## 워크플로우

1. **패키지 임포트**
   - 사용한 주요 패키지: pandas, seaborn, numpy, matplotlib, scikit-learn, OpenCV, tensorflow.keras

2. **데이터 로드 및 요약**
   - 데이터를 로드하여 기본적인 정보와 경로를 확인

3. **데이터 전처리**
   - 데이터 증강 및 전처리를 설정하여 모델 학습에 적합한 형태로 변환
   - 데이터 왜곡: 노이즈(컬러, 가우시안, 회색조), 변형(회전, 크기, 명암 대비, 찌그러뜨림, 크롭, 회색조)
   - 데이터 정규화: 증강된 데이터들을 한데 모아 정규화 진행

4. **스케일링 및 변수 변환**
   - 이미지 크기 조정 및 정규화를 통해 학습에 적합한 스케일로 변환

5. **탐색적 데이터 분석(EDA)**
   - 클래스 분포 시각화를 통해 데이터의 잠재적 구조를 파악

6. **모델 학습**
   - MobileNetV2, ResNet50, VGGNet16, DenseNet121 네 가지 모델을 학습하여 비교

7. **성능 평가 및 시각화**
   - Confusion Matrix 및 Classification Report 출력, ROC AUC 점수를 통해 성능 평가

## 프로젝트 결과

### 구현 기능
- 다양한 이미지 증강 기법을 통해 데이터 증강
- MobileNetV2, ResNet50, V의 성능 비교
- MobileNetV2가 가장 높은 성능(정확도 96%, F1-Score 0.96, ROC-AUC 0.95)을 기록하여 최적 모델로 선정

## 트러블 슈팅

- **오류**: "ValueError: Input size mismatch. Expected input batch size (None, 224, 224, 3) but got input batch size (None, 256, 256, 3)" - 이미지 크기 설정이 모델 입력 형식과 맞지 않아 발생한 오류
- **해결 방법**: 데이터 증강 및 전처리 단계에서 target_size=(224, 224)로 모든 이미지를 모델의 입력 형식에 맞춰 조정하여 오류 해결. 이미지 크기를 모델이 요구하는 입력 크기와 일치하도록 일괄적으로 변환하여 학습이 정상적으로 진행되도록 조정

## 프로젝트를 통해 얻은 역량

- 딥러닝 모델을 통한 이진 분류 문제 해결 및 모델 성능 최적화
- 이미지 데이터 전처리와 다양한 증강 기법을 통한 데이터 품질 개선
- 모델 성능 평가를 위한 다양한 지표(F1 Score, ROC-AUC 등) 활용
