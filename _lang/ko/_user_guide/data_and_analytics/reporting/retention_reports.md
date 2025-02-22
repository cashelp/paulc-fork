---
nav_title: 리텐션 보고서
article_title: 캠페인 및 캔버스에 대한 리텐션 보고서
page_order: 5
tool: Reports
page_type: reference
description: "이 참조 문서에서는 특정 캠페인 또는 캔버스에서 선택한 리텐션 이벤트를 수행한 사용자의 사용자 리텐션을 측정하는 방법에 대해 설명합니다."
---

# 리텐션 보고서

> 사용자 리텐션은 모든 마케터에게 가장 중요한 지표 중 하나입니다. 참여도가 높은 사용자가 계속 재방문한다는 것은 비즈니스가 건강하다는 것을 의미합니다. Braze를 사용하면 캠페인 또는 캔버스의 **애널리틱스** 페이지에서 바로 사용자 리텐션을 측정할 수 있습니다.

{% alert important %}
API 트리거 캠페인에는 유지 보고서를 사용할 수 없습니다.
{% endalert %}

## 리텐션 보고서 실행

### 1단계: 날짜 범위 선택

![보고 날짜][8]{: style="float:right;max-width:30%;margin-left:15px;"}

시작하려면 Braze 대시보드에서 캠페인이나 캔버스를 방문하여 보고서의 날짜 범위를 선택하세요. 적절한 날짜 범위를 선택하는 것은 유지 리포트에 영향을 미치기 때문에 매우 중요합니다. 

이 보고서에는 이 기간 동안 캠페인 또는 캔버스에 처음 입장한 모든 사용자가 포함되며, 해당 사용자 중 날짜 기간 동안 리텐션 이벤트를 수행한 사용자의 데이터가 보고서에 표시됩니다.

날짜 범위를 선택하려면 캠페인 또는 캔버스 **애널리틱스** 페이지의 오른쪽 상단 모서리로 이동해야 합니다. 여기에서 다양한 범위를 선택하거나 보고서에 대한 사용자 지정 범위를 설정할 수 있습니다.

### 2단계: 보존 이벤트 선택

{% tabs %}
{% tab 캠페인 %}

다음으로 아래로 스크롤하여 **캠페인 리텐션** 섹션으로 이동합니다. 캠페인 유지는 특정 캠페인을 수신한 사용자가 캠페인을 수신한 시점부터 30일 동안 유지 이벤트(유지 보고서에서 지정한)를 수행한 비율을 보여줍니다.

{% endtab %}
{% tab 캔버스 %}

그런 다음 페이지 하단의 **배리언트 상품 분석**을 클릭합니다. 여기에서 배리언트 상품을 분석하고, 퍼널 보고서를 확인하고, 유지 보고서를 확인할 수 있습니다. 캔버스 유지는 특정 캠페인을 수신한 사용자가 캔버스를 수신한 시점부터 30일 동안 유지 이벤트(유지 보고서에서 지정한)를 수행한 비율을 보여줍니다.

{% endtab %}
{% endtabs %}

![리텐션 이벤트 선택][1]{: style="max-width:80%"}

### 3단계: 보고서 생성

유지 이벤트를 선택한 후 **보고서 실행**를 클릭하여 쿼리를 시작합니다.

![보고서 실행][2]{: style="max-width:80%"}

이 쿼리는 결과를 생성하기 위해 검색해야 하는 데이터의 양에 따라 실행하는 데 몇 분 정도 걸릴 수 있습니다. 시간이 너무 오래 걸리면 보고서를 다시 로드해 보라는 알림이 표시됩니다. 보고서가 로드될 때까지 최대 5분 정도 기다려야 할 수 있습니다.

보고서가 생성된 후에는 24시간 동안 동일한 유지 이벤트로 다시 실행할 수 없습니다. 보고서가 마지막으로 생성된 날짜의 타임스탬프가 항상 표시되며, 하루 이상 경과한 경우 다시 생성할 수 있는 옵션이 제공됩니다. 그러나 리텐션 이벤트를 변경하고 보고서를 다시 실행하여 캠페인이 다른 KPI에 미치는 영향을 살펴볼 수 있습니다.

보고서에는 캠페인 또는 캔버스에서 메시지를 보낸 날짜만 나열됩니다. 일부 캠페인 및 캔버스의 경우, 보고서가 한 번만 전송된 경우 보고서가 하루만 표시될 수 있습니다. 반복되거나 트리거되는 경우 표에 여러 날짜가 표시될 수 있습니다.

{% tabs %}
{% tab 캠페인 %}

![보고서 전문]({% image_buster /assets/img/campaign_retention3.png %})

{% endtab %}
{% tab 캔버스 %}

![보고서 전문]({% image_buster /assets/img/canvas_retention_report.png %}){: style="max-width:70%"}

{% endtab %}
{% endtabs %}

## 보고서 설명

리텐션 보고서는 롤링 리텐션과 범위 리텐션 공식을 모두 제공합니다. 이러한 유지 유형 중 하나가 포함된 캠페인 또는 캔버스 보고서를 보려면 **유지 유형**에 대해 **롤링 유지** 또는 **범위 유지**를 선택합니다.

### 롤링 유지

롤링 유지는 보고서 상단에 나열된 날짜 또는 그 이후에 얼마나 많은 사용자가 다시 돌아와 유지 이벤트를 수행했는지 측정합니다. 따라서 사용자가 3일에서 7일 사이에 세션을 시작한 경우 사용자는 "3일", "1일", "0일" 열에서 유지된 것으로 계산됩니다. 캠페인 또는 캔버스가 전송된 시점으로부터 30일이 지난 후에 유지된 것으로 계산되는 모든 사용자는 해당 행의 "30일" 열 아래에 계산됩니다.

30일 이상의 기간 동안 여러 번 이벤트를 완료한 사용자는 여러 기간의 일부로 계산됩니다. 예를 들어, 1일 후에 세션을 완료한 사용자의 경우 >0 및 >1 열이 증가합니다. 3일 후에 이벤트를 완료하면 이전 열(>0 및 >1)에서 다시 증가하여 유지률이 100%를 초과할 수 있습니다.

#### 롤링 리텐션 보고서를 읽는 방법

3일차 열의 유지 보고서 차트를 읽는 방법은 Z일차에 캠페인을 받은 후 3일 이상 이벤트를 수행한 사용자 수(선택한 단위 기준)를 Y% 또는 Y로 표시하는 것입니다.

![롤링 리포트]({% image_buster /assets/img/campaign_retention3.png %})

또 다른 예로, 앞 이미지의 표를 참조하면 3월 25일에는 총 38명의 사용자가 유지 이벤트를 수행했습니다. 0일차 유지는 68.42%로, 캠페인을 받은 후 0일 이상(0일차 이후) 유지 이벤트를 수행한 사용자가 68.42%에 달했습니다. 7일차 유지는 57.89%로, 캠페인을 받은 후 7일 이상(7일차 이후) 이벤트를 실행한 사용자가 57.89%에 달했습니다.

이 정보는 첫 사용 후 30일 이상 제품을 사용한 사용자와 사용하지 않은 사용자의 비율을 알고자 할 때 유용할 수 있습니다. 30일 열의 백분율 또는 숫자 값은 30일 이후에 복귀한 사용자의 비율을 나타냅니다.

### 범위 유지

범위 유지는 보고서 상단에 나열된 일수 범위 내에서 얼마나 많은 사용자가 다시 방문했는지를 측정합니다. 따라서 사용자가 3일에서 7일 사이에 세션을 시작했다가 13일에 다시 세션을 시작한 경우 "3일-7일" 및 "7일-14일" 범위 모두에서 유지된 것으로 계산됩니다.

#### 범위 유지 보고서를 읽는 방법

범위 보고서는 가장 직관적으로 읽을 수 있는 보고서 중 하나입니다. 코호트의 모든 사용자 중 지정된 날짜 범위 내에서 유지 이벤트를 수행한 사용자의 비율을 명확하게 명시합니다. 예를 들어, 다음 이미지에서 모든 사용자 코호트를 참조하는 날짜 범위 "0일(0-24시간)"의 경우 코호트 중 35.71%가 유지 리포트를 수행했습니다. 사용자가 여러 날짜 범위 내에서 여러 개의 유지 이벤트를 수행하면 각 범위에 대해 유지된 것으로 계산됩니다.

![리텐션 보고서][5]

### 리텐션 보고서 구성 요소

- **사용자 열**: 표시되는 값은 선택한 기간 내에 시작 작업을 수행한 고유 사용자 수이며, 현재 사용자 수는 계산 중이므로 제외됩니다. 
- **코호트 Z 행**: 캠페인 또는 캔버스에서 메시지를 보낸 날짜를 표시합니다.
- **일 X 열**: 0일에서 30일 사이의 다양한 단위로 구성된 일수입니다.
- **모든 사용자 행**: 보고서 요약 행이라고도 하는 이 행은 전체 기간 동안의 유지 데이터를 요약합니다. 사용자가 여러 코호트에서 캠페인 또는 캔버스를 받은 경우, 그 결과는 여기에서 두 번 계산됩니다. 
- **백분율/숫자**: 캠페인 또는 캔버스를 받은 후 X일 이상 지난 Z일에 이벤트를 수행한 사용자의 백분율 또는 수를 표시합니다. 이 백분율은 가중 평균 백분율입니다. 불완전한 값은 별표로 표시됩니다.
- **날짜 범위**: 캠페인 또는 캔버스 **세부 정보** 페이지에서 설정한 날짜 범위에는 이 기간 동안 캠페인 또는 캔버스를 수신한 모든 사용자가 포함되며, 해당 사용자 중 날짜 범위 동안 리텐션 이벤트를 수행한 사용자의 데이터가 보고서에 표시됩니다.
- **단위**: 차트의 오른쪽 상단에서 사용자 비율과 사용자 수 사이의 단위를 조정할 수 있으며, 캠페인이나 캔버스의 영향력을 판단할 때 특정 단위가 더 중요할 수 있습니다.
- **색상 매핑**: 유지 보고서에서 사용자 수 또는 비율이 높을수록 파란색 음영이 진하게 지정됩니다. 비율이나 사용자 수가 낮을수록 더 밝은 파란색 음영이 할당됩니다. 이는 사용자가 이 데이터를 시각화할 수 있도록 돕기 위한 것입니다.
- **리텐션 보고서 그래프**: 이 그래프는 선택한 날짜 범위의 모든 코호트에 대한 결과를 요약한 것입니다.

### 배리언트 상품별 성능

배리언트 상품별 유지 보고서를 보면 선택한 기간 동안 각 배리언트 상품 또는 메시지 배리언트 상품에 대한 롤링 유지와 대조군을 비교할 수 있습니다. 이 보고서는 **성과 기준 표시**를 **배리언트 상품**별로 전환하여 볼 수 있습니다.

이형 상품별로 실적을 표시하는 몇 가지 사용 사례입니다:

- 결과가 노력 낭비처럼 보이거나 통계적으로 유의미하지 않은 변형 또는 실험이 있나요? 다시 한 번 살펴보고 어느 쪽이 더 롱테일 영향을 미치는지 확인하세요.
- 대조군의 유지 데이터를 분석하여 메시지를 보내지 않은 경우 유지율이 어떻게 되는지 확인하세요.

{% tabs %}
{% tab 캠페인 %}

![변형으로 보기]({% image_buster /assets/img/variant_view.png %})

{% endtab %}
{% tab 캔버스 %}

![변형으로 보기]({% image_buster /assets/img/variant_view_canvas.png %})

{% endtab %}
{% endtabs %}

#### 이형 상품 구성 요소별 리텐션 보고서

- **날짜 범위**: 캠페인 또는 캔버스 **세부 정보** 페이지에서 설정한 날짜 범위에는 이 기간 동안 캠페인 또는 캔버스를 받은 모든 사용자가 포함되며, 해당 사용자 중 날짜 범위 동안 리텐션 이벤트를 수행한 사용자의 데이터가 보고서에 표시됩니다. 매일 유지율, 대조군과의 변화율, 신뢰도를 측정합니다.
- **유지율**: 이형 상품별 리텐션 비율을 표시합니다. 유지율은 유지 이벤트를 수행한 사용자 수를 캠페인 또는 캔버스를 수신한 총 사용자 수로 나눈 값입니다.
- **대조군 대비 백분율 변화**: 대조군과의 배리언트 상품별 변화 비율을 정량화합니다.
- **신뢰도**: {% multi_lang_include metrics.md metric='신뢰도' %} Braze는 Z 테스트라는 통계 절차를 통해 각 이형 상품의 전환율과 대조 상품의 전환율을 비교하여 [신뢰도를]({{site.baseurl}}/user_guide/intelligence/multivariate_testing/#understanding-confidence) 계산합니다.
- **단위**: 차트의 오른쪽 상단에서 사용자 비율과 사용자 수 사이의 단위를 조정할 수 있으며, 캠페인이나 캔버스의 영향력을 판단할 때 특정 단위가 더 중요할 수 있습니다.
- **배리언트 그래프**: 이 그래프는 선택한 날짜 범위에 대한 변형별 결과를 요약한 것입니다.

## 리텐션 보고서에서 확인해야 할 사항

유지 보고서는 생성하기는 쉽지만 해석하고 조치를 취하기는 어렵습니다. 마케팅 담당자를 돕기 위해 리텐션 보고서를 볼 때 고려해야 할 몇 가지 주제와 질문을 정리해 보았습니다.

- 반복 캠페인의 요일별 추세를 고려합니다(예: 월요일 코호트가 토요일 코호트보다 실적이 더 좋은가요?).
- 영향력이 감소하기 시작하는 시점은 언제부터인가요? 이는 유지를 높이기 위해 해당 시점의 사용자를 타겟팅하는 새로운 캠페인이나 캔버스가 필요하다는 신호일 수 있습니다. 
- 메시징 피로를 느끼고 계신가요?
- 며칠 전에 캠페인이나 캔버스에 적용한 특정 최적화가 긍정적인 영향을 미쳤나요?

[1]: {% image_buster /assets/img/retention_1.png %}
[2]: {% image_buster /assets/img/retention_2.png %}
[5]: {% image_buster /assets/img/range_retention.png %}
[8]: {% image_buster /assets/img/date_select_retention.png %}


