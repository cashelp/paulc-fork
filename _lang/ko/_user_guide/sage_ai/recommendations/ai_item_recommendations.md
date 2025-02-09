---
nav_title: AI 항목 추천
article_title: AI 항목 추천
page_order: 15
alias: "/ai_item_recommendations/"
description: "이 참조 문서에서는 카탈로그의 품목에 대한 AI 품목 추천을 생성하는 방법에 대해 설명합니다."
---

# AI 항목 추천

> 카탈로그의 품목에 대한 AI 품목 추천을 생성하는 방법을 알아보세요.

AI 품목 추천을 사용하여 가장 인기 있는 제품을 계산하거나 특정 [카탈로그에]({{site.baseurl}}/user_guide/personalization_and_dynamic_content/catalogs/) 대한 개인화된 AI 추천을 생성할 수 있습니다. 추천을 생성한 후 개인화를 사용하여 해당 제품을 메시지에 삽입할 수 있습니다.

## 전제 조건

- 아래에 설명된 추천 유형을 사용하려면 \[카탈로그]] \[카탈로그] ]가 하나 이상 있어야 합니다.
- 카탈로그에 저장된 고유 제품 ID에 대한 참조가 포함된 구매 또는 이벤트 데이터(사용자 지정 이벤트 또는 구매 개체)가 Braze에 있어야 합니다.
- AI 개인화 추천은 수백 또는 수천 개의 항목과 일반적으로 구매 또는 상호 작용 데이터가 있는 최소 3만 명의 사용자를 대상으로 가장 잘 작동합니다. 이는 대략적인 가이드일 뿐이며 달라질 수 있습니다. 다른 추천 유형은 더 적은 데이터로 작동할 수 있습니다.

## AI 아이템 추천 만들기

아이템 추천을 만들려면 다음과 같이 하세요:

1. **애널리틱스** > **AI 항목 추천으로** 이동합니다.
2. **예측 생성** > **AI 항목 추천을** 선택합니다.

개별 카탈로그에서 바로 추천을 생성하도록 선택할 수도 있습니다. **카탈로그** 페이지에서 카탈로그를 선택하고 **추천 생성을** 클릭합니다.

### 1단계: 추천 세부 정보 추가

먼저 추천의 이름과 설명(선택 사항)을 입력합니다.

![][1]

### 2단계: 추천 정의 {#recommendation-type}

다음으로 추천 유형을 선택합니다. 모든 추천 유형은 지난 6개월간의 아이템 상호 작용(구매 또는 사용자 지정 이벤트) 데이터를 사용합니다. 아래에 언급된 상호 작용은 3단계에서 선택한 구매 이벤트 또는 사용자 지정 이벤트를 의미합니다.

- **가장 인기 있습니다:** 가장 많이 구매한 제품 등 작업 공간의 모든 사용자가 가장 자주 상호 작용하는 카탈로그에서 최대 30개의 항목을 계산합니다.
- **가장 최근:** 사용자가 가장 최근에 상호 작용한 최대 30개의 제품 목록을 생성합니다.
- **AI 개인화:** 새로운 종류의 딥 러닝인 트랜스포머를 사용하여 각 사용자가 다음에 상호작용할 가능성이 가장 높은 항목 세트를 예측합니다. 가능성이 가장 높은 항목부터 가장 낮은 항목까지 최대 30개까지 순위를 매깁니다. 이 유형의 추천은 대규모 언어 모델(LLM)을 사용하여 사용자의 데이터를 다른 Braze 고객의 데이터와 결합하지 않습니다.

{% alert tip %}
**가장 최근** 또는 **AI 개인 맞춤을** 사용하는 경우, 개인 맞춤 추천을 생성할 데이터가 부족한 사용자에게는 **가장 인기 있는** 항목이 대체 항목으로 제공됩니다. **가장 인기 있는** 폴백을 받는 사용자의 비율은 **애널리틱스** 페이지에 표시됩니다.
{% endalert %}

#### 2a단계: 이전 구매 또는 상호 작용 제외(선택 사항)

사용자가 이미 구매했거나 상호 작용한 아이템을 **추천하지 않**으려면 **사용자가 이전에 상호 작용한 아이템을 추천하지 않음을** 선택합니다. 이 옵션은 추천 **유형이** **AI 개인화로** 설정된 경우에만 사용할 수 있습니다.

![]\[2-3]

이 설정은 사용자가 이미 구매했거나 상호 작용한 항목이 최근에 업데이트된 경우 해당 추천이 다시 메시지에 표시되지 않도록 합니다. 추천 업데이트 사이에 구매하거나 상호작용한 항목이 계속 표시될 수 있습니다. 무료 버전의 항목 추천의 경우 매주 업데이트가 이루어집니다. 프로 버전의 AI 아이템 추천의 경우 24시간마다 업데이트가 이루어집니다.

예를 들어, 프로 버전의 AI 아이템 추천 기능을 사용할 때 사용자가 상품을 구매한 후 30분 이내에 마케팅 이메일을 수신하면 방금 구매한 상품이 제때 이메일에서 제외되지 않을 수 있습니다. 그러나 24시간 이후에 보낸 모든 메시지에는 해당 항목이 포함되지 않습니다.

#### 2b단계: 카탈로그 선택

아직 채워져 있지 않은 경우 이 권장 사항에서 항목을 가져올 \[카탈로그]] \[카탈로그] ]를 선택합니다.

#### 2c단계: 선택 항목 추가(선택 사항)

추천을 보다 세밀하게 제어하려면 사용자 지정 필터를 적용하는 [옵션을]({{site.baseurl}}/user_guide/personalization_and_dynamic_content/catalogs/selections/) 선택하세요. 선택 항목은 브랜드, 크기 또는 위치와 같은 카탈로그의 특정 열을 기준으로 권장 사항을 필터링합니다. Liquid가 포함된 선택 항목은 추천에 사용할 수 없습니다.

![]\[2-2]

{% alert tip %}
선택 항목을 찾을 수 없는 경우 먼저 카탈로그에 설정되어 있는지 확인하세요.
{% endalert %}

### 3단계: 추천을 유도할 상호 작용을 선택합니다.

그런 다음 이 권장 사항을 최적화할 이벤트를 선택합니다. 이 이벤트는 일반적으로 구매이지만 아이템과의 모든 상호작용일 수도 있습니다.

최적화할 수 있습니다:

- [구매 개체를]({{site.baseurl}}/api/objects_filters/purchase_object/) 사용한 구매 이벤트
- 구매를 나타내는 사용자 지정 이벤트
- 기타 항목 상호 작용(예: 제품 보기, 클릭 또는 미디어 재생)을 나타내는 사용자 지정 이벤트

**사용자 지정 이벤트를** 선택하는 경우 목록에서 이벤트를 선택합니다.

![][3]

### 4단계: 해당 속성 이름을 선택합니다. {#property-name}

추천을 생성하려면 카탈로그에서 항목의 `id` 필드와 일치하는 고유 식별자를 가진 상호작용 이벤트(구매 개체 또는 사용자 지정 이벤트)의 어떤 필드를 Braze에 알려야 합니다. 잘 모르시겠어요? [요구 사항 보기](#requirements).

**속성 이름에** 이 필드를 선택합니다.

**속성 이름** 필드에는 SDK를 통해 Braze로 전송된 필드 목록이 미리 채워집니다. 충분한 데이터가 제공되면 이러한 속성은 올바른 속성일 가능성이 높은 순서대로 순위가 매겨집니다. 카탈로그의 `id` 필드에 해당하는 것을 선택합니다.

![][4]

#### 요구 사항 {#requirements}

숙소를 선택하기 위한 몇 가지 요구 사항이 있습니다:

- 선택한 카탈로그의 `id` 필드에 매핑되어야 합니다.
- **객체 구매를 선택한 경우** `product_id` 또는 인터랙션 이벤트의 `properties` 필드여야 합니다.
- **사용자 지정 이벤트를 선택한 경우:** 사용자 지정 이벤트의 필드여야 합니다 `properties`.
- 중첩된 필드는 **속성 이름** 드롭다운에 `event_property.nested_property` 형식의 점 표기법으로 입력해야 합니다. 예를 들어 이벤트 속성 `location` 내에서 중첩된 속성 `district_name` 을 선택하는 경우 `location.district_name` 을 입력합니다.
- 필드는 배열(단일 이벤트 내의 여러 카탈로그 항목)로 구성될 수 있습니다. 자동으로 평평해집니다.

#### 매핑 예시

다음 예제 매핑은 모두 이 샘플 카탈로그를 참조합니다:

<style type="text/css">
.tg td{word-break:normal;}
.tg th{word-break:normal;font-size: 14px; font-weight: bold; background-color: #f4f4f7; text-transform: lowercase; color: #212123; font-family: "Sailec W00 Bold",Arial,Helvetica,sans-serif;}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top;word-break:normal}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-0pky">ID</th>
    <th class="tg-0pky">title</th>
    <th class="tg-0pky">가격</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky">ADI-BL-7</td>
    <td class="tg-0pky">아디다스 블랙 사이즈 7</td>
    <td class="tg-0pky">100.00 USD</td>
  </tr>
  <tr>
    <td class="tg-0pky">ADI-RD-8</td>
    <td class="tg-0pky">아디다스 레드 사이즈 8</td>
    <td class="tg-0pky">100.00 USD</td>
  </tr>
  <tr>
    <td class="tg-0pky">ADI-WH-9</td>
    <td class="tg-0pky">아디다스 화이트 사이즈 9</td>
    <td class="tg-0pky">100.00 USD</td>
  </tr>
  <tr>
    <td class="tg-0pky">ADI-PP-10</td>
    <td class="tg-0pky">아디다스 퍼플 사이즈 10</td>
    <td class="tg-0pky">75.00 USD</td>
  </tr>
</tbody>
</table>

{% tabs %}
{% tab 사용자 지정 이벤트 %}

고객이 결제하기 전에 유사한 제품을 추천할 수 있도록 사용자 지정 이벤트 `added_to_cart` 를 사용한다고 가정해 보겠습니다. 이벤트 `added_to_cart` 의 이벤트 속성은 `product_sku` 입니다.

그런 다음 `product_sku` 속성에는 샘플 카탈로그의 `id` 열에 있는 값 중 하나 이상이 포함되어야 합니다: "ADI-BL-7", "ADI-RD-8", "ADI-WH-9" 또는 "ADI-PP-10". 모든 카탈로그 항목에 이벤트가 필요한 것은 아니지만 추천 엔진이 작업할 수 있는 충분한 콘텐츠를 확보하기 위해 몇 가지 이벤트가 필요합니다.

##### 사용자 지정 이벤트 개체 예시

이 이벤트에는 샘플 카탈로그의 첫 번째 항목과 일치하는 `"product_sku": "ADI-BL-7"` 이 있습니다.

```json
{
  "events" : [
    {
      "external_id" : "user1",
      "app_id" : "your-app-id",
      "name" : "added_to_cart",
      "time" : "2024-07-16T19:20:30+01:00",
      "properties" : {
        "product_sku": "ADI-BL-7"
      }
    }
  ]
}
```

{% endtab %}
{% tab 구매 개체 %}

구매가 이루어지면 구매 객체가 API를 통해 전달됩니다.

매핑 측면에서는 사용자 지정 이벤트와 마찬가지로 구매 개체에도 비슷한 논리가 적용되지만, 구매 개체의 `product_id` 또는 `properties` 개체의 필드 중 하나를 선택할 수 있다는 점이 다릅니다.

모든 카탈로그 항목에 이벤트가 필요한 것은 아니지만, 추천 엔진이 충분한 콘텐츠를 확보할 수 있도록 몇 가지 이벤트는 필요하다는 점을 기억하세요.

##### 제품 ID에 매핑된 구매 개체 예시

이 이벤트에는 카탈로그의 첫 번째 항목에 매핑되는 `"product_id": "ADI-BL-7` 이 있습니다.

```json
{
  "purchases": [
    {
      "external_id": "user1",
      "app_id": "11ae5b4b-2445-4440-a04f-bf537764c9ad",
      "product_id": "ADI-BL-7",
      "currency": "USD",
      "price": 100.00,
      "time": "2024-07-16T19:20:30+01:00",
      "properties": {
        "color": "black",
        "checkout_duration": 180,
        "size": "7",
        "brand": "Adidas"
      }
    }
  ]
}
```

##### 속성 필드에 매핑된 구매 개체 예시

이 이벤트의 속성은 `"sku": "ADI-RD-8"` 이며, 카탈로그의 두 번째 항목에 매핑됩니다.

```json
{
  "purchases": [
    {
      "external_id": "user1",
      "app_id": "11ae5b4b-2445-4440-a04f-bf537764c9ad",
      "product_id": "shoes",
      "currency": "USD",
      "price": 100.00,
      "time": "2024-07-16T19:20:30+01:00",
      "properties": {
        "sku": "ADI-RD-8",
        "color": "red",
        "checkout_duration": 180,
        "size": "8",
        "brand": "Adidas"
      }
    }
  ]
}
```

{% endtab %}
{% endtabs %}

### 5단계: 추천 훈련

준비가 완료되면 **추천 생성을** 선택합니다. 이 과정을 완료하는 데 10분에서 36시간까지 걸릴 수 있습니다. 추천이 성공적으로 학습되면 이메일 업데이트를 받거나 생성에 실패한 이유에 대한 설명을 받게 됩니다.

**예측** 페이지에서 추천을 찾은 다음 필요에 따라 편집하거나 보관할 수 있습니다. 추천은 매월 한 번씩 자동으로 재교육됩니다.

## 분석

추천에 대한 분석을 확인하여 사용자에게 추천된 항목과 추천 모델이 얼마나 정확한지 확인할 수 있습니다.

1. **애널리틱스** > **항목 추천으로** 이동합니다.
2. 목록에서 추천을 선택합니다.

페이지 상단에서 정확도 및 범위와 같은 추천에 대한 통계를 확인할 수 있습니다.

![][5]

이러한 메트릭은 다음 표에 정의되어 있습니다. 

| Metric              | 설명 |
| ------------------- | ---------- |
| 정밀도           | 모델이 사용자가 구매한 다음 항목을 정확히 맞춘 시간의 백분율입니다. 정확도는 특정 카탈로그 크기와 믹스에 따라 크게 달라지며, 모델이 얼마나 자주 정확한지 파악하기 위한 가이드로 사용해야 합니다.<br><br>과거 테스트에서 6~20% 범위의 정밀도 수치로 모델이 잘 작동하는 것을 확인했습니다. 이 메트릭은 모델이 다음에 재학습할 때 업데이트됩니다.  |
| 범위            | 카탈로그에서 사용 가능한 품목 중 최소 한 명의 사용자에게 추천되는 비율입니다. 가장 인기 있는 항목보다 개인화된 항목 추천을 통해 더 높은 항목 커버리지를 기대할 수 있습니다. |
| 추천 유형 | 가장 인기 있는 항목의 폴백 대비 개인화된 추천 또는 최신 추천을 받게 되는 사용자의 비율입니다. 폴백은 개인화되거나 가장 최근의 추천을 생성하기에 충분한 데이터가 없는 사용자에게 전송됩니다. |
{: .reset-td-br-1 .reset-td-br-2}

다음 섹션에서는 카탈로그의 항목을 두 개의 가능한 열로 나누어 분석합니다:

- **맞춤 설정된 항목** 또는 **가장 최근 항목:** 이 열에는 카탈로그의 각 항목이 사용자에게 가장 자주 추천되는 순서대로 내림차순으로 나열됩니다. 이 열에는 모델에 의해 각 항목에 할당된 사용자 수도 표시됩니다.
- **가장 인기 있는 아이템:** 이 열에는 카탈로그의 각 항목이 인기도에 따라 내림차순으로 나열됩니다. 여기서 인기도는 전체 작업 공간에서 사용자가 가장 자주 상호 작용하는 카탈로그의 항목을 의미합니다. 가장 인기 있는 항목은 개별 사용자에 대한 맞춤 설정 또는 가장 최근 항목을 계산할 수 없을 때 대체 항목으로 사용됩니다.

![][6]

**권장** 사항 **개요에는** 권장 사항이 마지막으로 업데이트된 시기를 포함하여 선택한 권장 사항 구성의 요약이 표시됩니다.

![][7]{: style="max-width:45%" }

## 메시징에서 권장 사항 사용

![][10]{: style="max-width:30%;float:right;margin-left:15px;"}

추천 교육이 끝나면 Liquid로 메시지를 개인화하여 해당 카탈로그에서 가장 인기 있는 제품을 삽입할 수 있습니다. 리퀴드는 메시지 작성기에 있는 개인화 창에서 생성할 수 있습니다:

1. 개인 설정을 지원하는 모든 메시지 작성기에서 다음을 클릭합니다. <i class="fa-solid fa-circle-plus" style="color: #12aec5;" title="맞춤 설정 추가"></i> 을 클릭하여 개인화 창을 엽니다.
2. **개인화 유형에서** **항목 추천을** 선택합니다.
3. **항목 권장 사항 이름에서** 방금 만든 권장 사항을 선택합니다.
4. **예상 품목 수에** 삽입할 상위 제품 수를 입력합니다. 예를 들어 가장 많이 구매한 상위 3개 항목을 표시할 수 있습니다.
5. **표시할 정보의** 경우 카탈로그에서 각 항목에 포함할 필드를 선택합니다. 각 항목에 대한 이러한 필드의 값은 이 권장 사항과 관련된 카탈로그에서 가져옵니다.
6. **복사** 아이콘을 클릭하고 메시지에서 원하는 위치에 리퀴드를 붙여넣습니다.

## AI 항목 추천 계층

다음 표에서는 무료 버전과 프로 버전의 AI 아이템 추천의 차이점을 설명합니다:

| 영역                   | 무료 버전                          | 프로 버전            |
| :---------------------- | ------------------------------------- | :--------------------------------------- |
| 사용자 업데이트 <sup>빈도1</sup>   | 주별                                | 일별                                    |
| 모델 재교육 빈도  | 월별                               | 월별                                   |
| 최대 권장 사항 | <sup>유형별</sup> 권장 사항 1개1 | <sup>유형별</sup> 권장 사항 100개2 |

<sup>1\. 사용자별 항목 추천이 업데이트되는 빈도입니다(모델이 재학습할 때 업데이트되는 가장 인기 있는 항목을 제외한 모든 모델). 예를 들어, 사용자가 AI 아이템 추천을 기반으로 추천된 아이템을 구매하면 이 빈도에 따라 추천 아이템이 업데이트됩니다.</sup>
<sup>2\. 사용 가능한 추천 유형은 AI 맞춤, 가장 최근, 가장 인기 있는 것입니다.</sup>

## 자주 묻는 질문

### '가장 인기 있는' 항목이 다른 모델의 추천 항목에 섞여 있는 이유는 무엇인가요?

추천 엔진이 목록을 큐레이션할 때는 먼저 '가장 최근' 또는 'AI 개인화' 등 사용자가 선택한 특정 모델을 기반으로 개인화된 선택 항목의 우선순위를 지정합니다. 어떤 이유로든 30개의 추천 목록 전체를 채울 수 없는 경우, 모든 사용자에게 가장 인기 있는 항목이 추가되어 각 사용자에게 항상 전체 추천 목록이 제공되도록 합니다.

이는 몇 가지 특정 조건에서 발생합니다:

- 모델은 기준과 일치하는 항목이 30개 미만인 항목을 찾습니다.
- 관련 상품이 더 이상 제공되지 않거나 재고가 없습니다.
- 재고 또는 사용자 선호도 변경으로 인해 현재 선택 기준에 맞지 않는 상품이 있습니다.

[1]: {% image_buster /assets/img/item_recs_1.png %}
\[2-1]: {% image_buster /assets/img/item_recs_2-1.png %}
\[2-2]: {% image_buster /assets/img/item_recs_2-2.png %}
\[2-3]: {% image_buster /assets/img/item_recs_2-3.png %}
[3]: {% image_buster /assets/img/item_recs_3.png %}
[4]: {% image_buster /assets/img/item_recs_4.png %}
[5]: {% image_buster /assets/img/item_recs_analytics_1.png %}
[6]: {% image_buster /assets/img/item_recs_analytics_2.png %}
[7]: {% image_buster /assets/img/item_recs_analytics_3.png %}
[10]: {% image_buster /assets/img/add_personalization.png %}
\[catalog]: {{site.baseurl}}/user_guide/personalization_and_dynamic_content/catalogs/
