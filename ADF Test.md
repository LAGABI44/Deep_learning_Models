# ADF Test ( Augmented Dickey-Fuller Test )

## 1. ADF Test란?
- 1979년 David Dickey와 Wayne Fuller에 의해 개발된 DF Test를 일반화한 검정   
  => Dickey-Fuller Test는 단위근이 존재한다는 귀무가설을 통계적으로 검정하는 방법   
y _t=c+βt+αy_{t−1}+ϕ∇y_{t−1}+e_t   
![DF Test](https://user-images.githubusercontent.com/96757866/154507210-f9fa5eac-5735-41ad-9004-e8fea0c22382.png)
    - c : 시계열 데이터의 레벨   
    - β : 시계열 데이터의 추세항   
    - 각 파라미터를 regression으로 추정해 \alphaα가 단위근을 가질 확률을 검정함   
    - α=1이면 단위근을 가지는 것이기 때문에 정상성을 띠지 않는다고 판단   
- ADF Test는 DF Test 식에서  p lag의 차분을 추가해 검정 능력을 더욱 강화   
y _t=c+βt+αy_{t−1}+ϕ _1∇y _{t−1}+...+ϕ_p∇y_{t−p}+e_t 
![ADF Test](https://www.machinelearningplus.com/wp-content/uploads/2019/11/equation_3-1024x114.png)
    - t−p 시점까지의 차분 경향성을 파악할 수 있어서 주기를 가진 데이터의 정상성 여부 판단 가능   
- 정상성을 알아보기 위한 단위근 검정 방법   
  => 단위근(unit root)은 x=1, y=1인 해로, 시계열 자료에서 예측할 수 없는 결과를 가져올 수 있다.   
- 검정통계량이 Critical Value보다 작거나 p-value가 설정한 유의수준 값보다 작으면 정상적인 시계열 데이터라 판단   
- [ADF Test 자세히 알아보기](https://www.machinelearningplus.com/time-series/augmented-dickey-fuller-test/)

***
## 2. 귀무가설 vs 대립가설
- 귀무가설( Null hypothesis:H0)
  - 통계학에서 처음부터 버릴 것을 예상하는 가설
  -  “모집단의 모수는 00와 같다.” 또는 “ 모집단의 모수는 00와 차이가 없다.” 라고 가정
  -   “~와 차이가 없다.” “~의 효과가 없다.” “~와 같다.” 라는 형식으로 설정
- 대립가설( Alternative hypothesis:H1)
  - 귀무가설이 거짓이라면 대안적으로 참이 되는 가설
  -  “모집단의 모수는 00와 다르다.” 또는 “ 모집단의 모수는 00와 차이가 있다.” 라고 가정
  -  “~와 차이가 있다.” “~의 효과는 있다.” “~와 다르다.” 라는 형식으로 설정

***
## 3. p-value
- 귀무가설이 참이라고 가정했을 때, 표본으로 얻어지는 통계치(예: 표본 평균)가 나타날 확률
- p값이 낮다는 것은 귀무가설이 참이라는 가정 하에서 표본을 추출했을 때, 이런 표본 평균이 관측될 확률이 낮다는 것을 뜻함
  => 즉 p 값이 매우 낮으면, 이러한 표본 통계량은 우연히 나타나기 어려운 케이스이기 때문에, 우리는 귀무가설을 채택하지 않고(기각하고), 대안적인 가설, 즉 대립가설을 채택하게 됩니다.
- [유의확률](https://ko.wikipedia.org/wiki/%EC%9C%A0%EC%9D%98_%ED%99%95%EB%A5%A0), [p-value](https://yeomko.tistory.com/37)
![p-value](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fb23NHy%2FbtqDA5oG65i%2FQUZe3SOdsocNOZHo6afm41%2Fimg.png)
- p 값이 0에 가까울수록 귀무가설의 설득력은 점점 약해지고 이를 기각하고 우리가 입증하고 싶은 대립 가설의 설득력은 점점 강해지게 됨

***
## 4. statsmodels 패키지
-  R에서 제공하는 통계검정, 시계열분석 등의 기능을 파이썬에서도 이용할 수 있도록 하는 강력한 통계 패키지
-  statsmodels 패키지에서 제공하는 adfuller 메서드를 이용해 ADF Test를 진행한 code
```
from statsmodels.tsa.stattools import adfuller

def augmented_dickey_fuller_test(timeseries):
    # statsmodels 패키지에서 제공하는 adfuller 메서드를 호출합니다.
    dftest = adfuller(timeseries, autolag='AIC')  
    
    # adfuller 메서드가 리턴한 결과를 정리하여 출력합니다.
    print('Results of Dickey-Fuller Test:')
    dfoutput = pd.Series(dftest[0:4], index=['Test Statistic','p-value','#Lags Used','Number of Observations Used'])
    for key,value in dftest[4].items():
        dfoutput['Critical Value (%s)' % key] = value
    print(dfoutput)
```
