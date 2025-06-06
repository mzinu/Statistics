# 통계학 7주차 정규과제

📌통계학 정규과제는 매주 정해진 분량의 『*데이터 분석가가 반드시 알아야 할 모든 것*』 을 읽고 학습하는 것입니다. 이번 주는 아래의 **Statistics_7th_TIL**에 나열된 분량을 읽고 `학습 목표`에 맞게 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 추가자료와 교재를 다시 참고하여 보완하는 것이 좋습니다.

7주차는 `3부. 데이터 분석하기`를 읽고 새롭게 배운 내용을 정리해주시면 됩니다.


## Statistics_7th_TIL

### 3부. 데이터 분석하기
### 13.머신러닝 분석 방법론
### 14.모델 평가



## Study Schedule

|주차 | 공부 범위     | 완료 여부 |
|----|----------------|----------|
|1주차| 1부 p.2~56     | ✅      |
|2주차| 1부 p.57~79    | ✅      | 
|3주차| 2부 p.82~120   | ✅      | 
|4주차| 2부 p.121~202  | ✅      | 
|5주차| 2부 p.203~254  | ✅      | 
|6주차| 3부 p.300~356  | ✅      | 
|7주차| 3부 p.357~615  | ✅      | 

<!-- 여기까진 그대로 둬 주세요-->

# 13.머신러닝 분석 방법론

```
✅ 학습 목표 :
* 선형 회귀와 다항 회귀를 비교하고, 데이터를 활용하여 적절한 회귀 모델을 구축할 수 있다. 
* 로지스틱 회귀 분석의 개념과 오즈(Odds)의 의미를 설명하고, 분류 문제에 적용할 수 있다.
* k-means 알고리즘의 원리를 설명하고, 적절한 군집 개수를 결정하여 데이터를 군집화할 수 있다.
```

## 13.1. 선형 회귀분석과 Elastic Net(예측모델)
- 선형 회귀분석
    - 독립 변수와 종속 변수 간의 선형 관계를 모델링하는 기법
    - 주로 두 변수 사이의 관계를 예측하거나 설명
    - 기본 가정 : 독립 변수와 종속 변수 간의 관계가 직선으로 나타날 수 있으며, 이때 회귀 계수는 최소 제곱법을 통해 추정
    - 실제 데이터에서는 이러한 가정이 항상 성립 X -> 다중공선성 문제나 과적합 문제 등이 발생
- Elastic Net(선형회귀의 단점 보완)
    - Lasso와 Ridge 회귀의 장점을 결합
    - 변수 선택과 모델의 일반화 능력을 동시에 개선
    - 특히 고차원 데이터나 다중공선성이 존재하는 데이터 세트에서 효과적
    - L1 규제와 L2 규제를 동시에 적용하여 변수 선택의 유연성↑ 과적합 방지 -> 모델의 예측 성능을 향상

## 13.2. 로지스틱 회귀분석 (분류모델)
- 이진 분류 문제를 해결하는 데 사용
- 독립 변수를 사용하여 종속 변수의 범주를 예측
- 선형 회귀와 달리 결과 변수가 범주형이며, 특히 두 가지 범주로 나누어지는 경우에 사용
- 예측된 확률을 0과 1 사이로 제한 -> 결과가 명확한 범주로 구분
    - EX. 특정 이메일이 스팸인지 아닌지를 예측
- 오즈 비율
    - 독립 변수의 변화가 종속 변수에 미치는 영향을 이해 -> 의사결정, 정책 수립에 중요한 통찰력 제공
    - 변수의 중요도를 판단 -> 모델 해석 용이
- 데이터가 선형적으로 분리될 수 있는 경우에 적합

## 13.8. k-means 클러스터링(군집모델)
- 비지도 학습 알고리즘
- 데이터 포인트를 여러 개의 군집으로 나누는 데 사용
- 각 데이터 포인트를 가장 가까운 군집 중심에 할당하여 군집 형성
- 과정
    - 초기 : k개의 군집 중심이 무작위로 설정, 각 데이터 포인트는 가장 가까운 군집 중심에 할당.
    - 군집 중심은 해당 군집에 속한 데이터 포인트의 평균으로 업데이트
    - 수렴할 때까지 반복
- 데이터의 패턴을 파악하고, 데이터의 구조를 이해하는 데 효과적
    - EX. 고객 세분화, 이미지 압축, 이상치 탐지 등
- 군집 수 k를 미리 지정 -> 엘보우 방법이나 실루엣 분석 사용
- 구형의 군집을 가정 -> 비구형의 군집을 가지는 데이터에서는 성능↓


# 14. 모델 평가

```
✅ 학습 목표 :
* 유의확률(p-value)을 해석할 때 주의할 점을 설명할 수 있다.
* 분석가가 올바른 주관적 판단을 위한 필수 요소를 식별할 수 있다.
```

## 14.3. 회귀성능 평가지표
- 회귀 모델의 예측력을 평가하는 데 사용되는 다양한 통계적 지표
- 결정계수(R^2), 평균 제곱 오차(MSE), 평균 제곱근 오차(RMSE), 평균 절대 오차(MAE) 등
- 모델이 종속 변수의 변동성을 얼마나 잘 설명하는지를 나타냄
- 1에 가까울수록 모델의 설명력이 뛰어남
- 종류
    - MSE
        - 예측값과 실제값 사이의 차이를 제곱하여 평균한 값
        - 값이 작을수록 모델의 예측이 실제값에 가까움
    - RMSE
        - MSE의 제곱근
        - 예측 오차를 원래 데이터의 단위로 표현하여 해석을 용이하게 함
    - MAE
        - 예측값과 실제값 사이의 절대 차이의 평균
        - 이상치에 덜 민감

## 14.6. 유의확률의 함정
- 유의확률 : 통계적 가설 검정에서 널리 사용
- 귀무가설이 참이라는 가정 하에 관측된 데이터와 같은 극단적인 결과가 나타날 확률
- 유의점
    - p-value가 작다고 해서 귀무가설이 거짓이라는 것을 확신할 수 없음
        - 단지 데이터가 귀무가설과 일치하지 않을 가능성을 시사
    - p-value는 샘플 크기에 민감
        - 큰 샘플에서는 작은 효과도 통계적으로 유의하게 나타날 수 있음/작은 샘플에서는 큰 효과도 유의하지 않게 나타날 수 있음
        - p-value만을 기반으로 결론을 내리는 것은 위험 -> 효과 크기나 신뢰 구간과 같은 추가 정보를 함께 고려하는 것이 중요
        - 연구자의 주관적인 판단과 연구 맥락 이해해야함

## 14.7. 분석가의 주관적 판단과 스토리텔링
- 분석가 : 데이터를 해석하고, 그 결과를 이해하기 쉽게 전달해야 하는 책임
    - 수치나 통계적 결과를 제시 + 데이터를 기반으로 한 스토리텔링
    - 데이터의 맥락을 이해하고, 분석 결과를 통해 어떤 메시지를 전달할 것인지 명확히 해야함
    - 다양한 시각적 도구와 프레젠테이션 기법을 활용
    - 데이터의 제한 사항이나 불확실성을 솔직하게 전달
- 스토리텔링 : 데이터 분석의 결과를 청중에게 효과적으로 전달 + 복잡한 정보를 쉽게 이해할 수 있도록 도움
- 청중이 데이터 분석의 결과를 더 잘 이해하고, 그에 따른 의사결정을 내릴 수 있게 함 + 깊이 있는 통찰력 제공

<br>
<br>

# 확인 문제

## **문제 1. 선형 회귀**

> **🧚 칼 피어슨의 아버지와 아들의 키 연구 결과를 바탕으로, 다음 선형 회귀식을 해석하세요.**  
> 칼 피어슨(Karl Pearson)은 아버지(X)와 아들(Y)의 키를 조사한 결과를 바탕으로 아래와 같은 선형 회귀식을 도출하였습니다. 아래의 선형 회귀식을 보고 기울기의 의미를 설명하세요. 
>  
> **ŷ = 33.73 + 0.516X**  
>   
> - **X**: 아버지의 키 (cm)  
> - **ŷ**: 아들의 예상 키 (cm)  

```
아버지의 키가 1cm 증가할 때 아들의 예상 키가 0.516cm 증가함을 의미. 즉, 아버지의 키가 아들의 키에 미치는 영향을 나타내는 계수. 기울기가 양수이므로, 아버지의 키가 클수록 아들의 키도 더 클 가능성이 높음을 시사함.
```
---

## **문제 2. 로지스틱 회귀**  

> **🧚 다트비에서는 학생의 학업 성취도를 예측하기 위해 다항 로지스틱 회귀 분석을 수행하였습니다. 학업 성취도(Y)는 ‘낮음’, ‘보통’, ‘높음’ 3가지 범주로 구분되며, 독립 변수는 주당 공부 시간(Study Hours)과 출석률(Attendance Rate)입니다. 단, 기준범주는 '낮음' 입니다.**   

| 변수 | Odds Ratio Estimates | 95% Wald Confidence Limits |  
|------|----------------------|--------------------------|  
| Study Hours | **2.34** | (1.89, 2.88) |  
| Attendance Rate | **3.87** | (2.92, 5.13) |  

> 🔍 Q1. Odds Ratio Estimates(오즈비, OR)의 의미를 해석하세요.

<!--변수 Study Hours의 오즈비 값이 2.34라는 것과 Attendance Rate의 오즈비 값이 3.87이라는 것이 각각 무엇을 의미하는지 구체적으로 생각해보세요.-->

```
주당 공부 시간의 오즈비는 2.34로, 이는 주당 공부 시간이 1단위 증가할 때, 성취도가 '낮음'에서 '보통'이나 '높음'으로 상승할 가능성이 2.34배 증가함을 의미함.
출석률의 오즈비는 3.87로, 이는 출석률이 1단위 증가할 때, 성취도가 '낮음'에서 '보통'이나 '높음'으로 상승할 가능성이 3.87배 증가함을 의미합니다.
```

> 🔍 Q2. 95% Wald Confidence Limits의 의미를 설명하세요.
<!--각 변수의 신뢰구간에 제시된 수치가 의미하는 바를 생각해보세요.-->

```
주당 공부시간 오즈비의 95% 신뢰구간은 (1.89, 2.88)로, 이는 주당 공부 시간의 실제 오즈비가 이 범위 내에 포함될 가능성이 95%라는 것을 의미함. 즉, 주당 공부 시간이 증가할 때 성취도의 변화율이 이 범위 내에 있을 것으로 95% 확신할 수 있음.
출석률 오즈비의 95% 신뢰구간은 (2.92, 5.13)로, 이는 출석률의 실제 오즈비가 이 범위 내에 포함될 가능성이 95%라는 것을 의미함. 즉, 출석률이 증가할 때 성취도의 변화율이 이 범위 내에 있을 것으로 95% 확신할 수 있음.
```

> 🔍 Q3. 이 분석을 기반으로 학업 성취도를 향상시키기 위한 전략을 제안하세요.
<!--Study Hours와 Attendance Rate 중 어느 변수가 학업 성취도에 더 큰 영향을 미치는지를 고려하여, 학업 성취도를 향상시키기 위한 효과적인 전략을 구체적으로 제시해보세요.-->

```
출석률이 더 높은 오즈비를 가지고 있으므로, 상대적으로 더 큰 영향을 미친다고 판단하였음.

출석률 개선 프로그램: 학생들의 출석률을 높이기 위한 상벌점 제도 도입
```

---


## **문제 3. k-means 클러스터링**

> **🧚 선교는 고객을 유사한 그룹으로 분류하기 위해 k-means 클러스터링을 적용했습니다. 초기에는 3개의 군집으로 설정했지만, 결과가 만족스럽지 않았습니다. 선교가 최적의 군집 수를 찾기 위해 사용할 수 있는 방법을 한 가지 이상 제시하고 설명하세요.**

```
1. 엘보우 방법 (Elbow Method)
   - 군집 수에 따른 총 군집 내 제곱합을 계산하여, SSE가 급격히 감소하는 지점을 찾는 방법.
   - 군집 수를 증가시킬수록 SSE는 감소하지만, 어느 시점 이후로는 감소 폭이 줄어들게 되는데, 이때의 군집 수를 최적의 군집 수로 간주

2. 실루엣 분석 (Silhouette Analysis)
   - 각 데이터 포인트의 클러스터링 품질을 평가하는 방법
   - 실루엣 계수는 -1에서 1 사이의 값을 가지며, 1에 가까울수록 잘 군집화되었다는 것을 의미
   - 최적의 군집 수는 평균 실루엣 계수가 가장 높은 군집 수로 결정
```

### 🎉 수고하셨습니다.
