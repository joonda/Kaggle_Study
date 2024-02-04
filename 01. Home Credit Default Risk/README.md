# Home_Credit Default Risk
## Infomation
* application_train, previous_application 데이터를 활용하여 시각화
  * bar, pie chart 활용
* Categorical Feature는 Label Encoder 진행
* Model은 RandomForest로 진행

## Conclustion
* Feature Importances 에서는 EXT_SOURCE_2, EXT_SOURCE_3, EXT_SOURCE_1 가 가장 높음.

## Thinking
* 데이터의 컬럼이 많은 편이고, 금융 관련 도메인이라 어려운 Notebook이었지만, 필사를 진행하며 다양한 chart를 다시 접할 수 있어 좋았다.
* Pie chart를 사용할 때, 0.00~% 등 작은 값 같은 경우 보는 입장에서 방해가 될 수 있기에 처리가 필요하다는 것을 인지했다.
  * 극소수의 데이터라면 삭제도 고려해볼 수 있다
  * 근처의 값과 더하여 A+B로 표현하는 방법도 고려해볼 수 있다.
* Bar chart에서 다른 값이 너무 커서 낮은 값은 가려지거나 안보이는 경우도 발생.
  * 합치는 것도 방법이지만, 작은 값들의 분포를 보고 싶다면 값이 너무 큰 데이터는 제외하고 시각화를 하는 방법도 고려해볼 수 있다. 
  (특히 불균형이 심할 시, 효과적으로 사용가능)

## Addtional
* Feature Importances 진행시, EXT_SOURCE가 외부 수입원으로 유추가 되는데, 대출 상환 여부를 예측하는 점에서 어느정도는 이해는 가지만, 왜 이렇게 높게 찍힐까? 
* One Hot Encoder 같은 경우는 컬럼수가 너무 방대해져서 Lable Encoder를 사용한 것으로 추정.
* train에서 NaN 값을 -999로 처리한 점을 확인 가능
* 데이터의 불균형이 심한 상태, 이를 처리하는 것이 필요하지 않을까?
* iplot으로 시각화 하는 것이 matplotlib으로 시각화 하는 것보다 좀 더 효과적일까?
------
## `Pearson Correlation Coefficient (피어슨 상관계수)`
* **두 척도변인 간의 선형관계를 정량화하는 통계치**
* 표본 데이터에 근거한 통계치일시 $r$, 전집에 근거한 통계치일 시 $p$로 표기한다.
* 코시-슈바르츠 부등식에 의해 +1과 -1 사이의 값을 가진다.
# $r$ = $\frac{\sum[(X-M_{x})(Y-M_{y})]} {\sqrt{(SS_{x})(SS_{y})}}$ = $\frac{\sum[(X-M_{x})(Y-M_{y})]} {\sqrt{\sum(X-M_{x})^2} \sqrt{\sum(Y-M_{y})^2}}$ 
* $M_{x}$ → $X$ 평균, $M_{y}$ → $Y$ 평균,
* 분자 : 두 변인의 편차를 곱하여 모두 더한 값
* 분모 : 두 변인의 제곱합을 곱한 값
