---
nav_title: 프롬프트에 대하여
article_title: AI Liquid Assistant에 대한 프롬프트
description: "이 기사에서는 AI Liquid Assistant를 프롬프트하는 방법, 모범 사례 및 예제 프롬프트를 다룰 것입니다."
page_type: reference
page_order: 0
hidden: true
permalink: /ai_liquid_prompts/
noindex: true
---

# AI Liquid Assistant에 대한 프롬프트 작성

> 프롬프트는 AI Liquid Assistant에게 원하는 작업을 명확하게 지시하는 과정입니다.

{% alert important %}
AI Liquid Assistant는 현재 푸시 및 SMS 채널을 적극적으로 사용하는 제한된 수의 고객을 대상으로 베타 버전으로 제공되고 있습니다. 베타에 고려되는 것에 관심이 있으시면 고객 성공 매니저에게 연락하거나 이 [포털 카드](https://braze.productboard.com/entity-detail/features/27273918)에 관심을 표시하십시오.
{% endalert %}

AI Liquid Assistant는 Braze와 Liquid를 사용하여 영향력 있는 마케팅 메시지를 만드는 전문가인 최고 수준의 마케터로 설계되었지만, 여전히 특정 사용 사례나 질문에 대한 지침이 필요합니다.

비서를 프롬프트하는 올바른 방법은 하나만 있는 것이 아니며, 대화 중에 프롬프트에 추가 세부 정보를 항상 추가할 수 있습니다. 이는 '완벽한' 초기 프롬프트를 작성하는 데 많은 시간을 할애할 필요가 없음을 의미합니다. 하지만 몇 가지 모범 사례를 따르면 어시스턴트를 최대한 활용할 수 있습니다.

## 효과적인 프롬프트를 위한 모범 사례

### 자연어를 사용하세요

AI Liquid Assistant는 자연어를 이해하도록 훈련되었습니다. 도움이 필요할 때 동료에게 묻는 것처럼 그것과 대화하세요. 이것은 어시스턴트가 귀하의 요구를 이해하고 정확한 도움을 제공하기 쉽게 만듭니다.

### 맥락을 제공하십시오

맥락을 제공하면 AI Liquid Assistant가 프로젝트를 둘러싼 더 큰 그림을 이해하는 데 도움이 됩니다. 다음과 같은 맥락을 포함하는 것이 도움이 됩니다:

- 귀하의 회사 이름 및 산업
- 당신이 작업 중인 캠페인, 예를 들어 블랙 프라이데이 또는 휴일 세일
- 귀하의 목표, 예를 들어 클릭률을 높이는 것
- 특정 커스텀 속성을 메시지에 포함하려는 경우

귀하의 요청에 문맥을 포함하면 어시스턴트가 귀하의 요구에 더 잘 맞는 응답을 제공할 수 있습니다. 캠페인, 메시지 요약 또는 브레인스토밍 문서의 세부 정보를 포함하여 어시스턴트가 최신 정보를 얻을 수 있도록 할 수 있습니다.

### 구체적으로 말하세요

AI Liquid Assistant는 후속 질문을 할 수 있지만, 세부 정보를 미리 제공하면 더 정확한 결과를 더 빨리 얻을 수 있습니다. 세부 사항을 포함하는 것을 고려하십시오:

- 알려진 선호 사항이나 메시지에 대한 요구 사항
- 메시지 수신자로부터 응답이 없는 상황이나 대체 메시지 옵션과 같은 상황을 처리하는 방법에 대한 지침
- 연결된 콘텐츠를 사용하는 Liquid, API 엔드포인트에 대한 설명서, 샘플 API 응답 또는 둘 다 요청할 때

### 창의력을 발휘하세요

당신의 메시징을 향상시키기 위해 AI Liquid Assistant가 어떻게 작동하는지 확인하려면 고정관념을 깨고 생각해 보세요. 다양한 프롬프트와 아이디어를 실험해 보세요. 창의성은 더 매력적인 결과를 가져올 수 있습니다.

## 예시 프롬프트

새로운 아이디어가 필요하신가요? 아래의 프롬프트를 확인하고 시도해 보세요 (또는 원하는 대로 조정하세요).

### 일반 정보

- Liquid이 무엇이며 Braze 내 마케팅 캠페인의 개인화를 어떻게 향상시킬 수 있습니까?
- Liquid에서 마케팅 메시지를 개인화하기 위해 인구 통계 정보나 과거 구매와 같은 어떤 유형의 데이터를 사용할 수 있습니까?

### 개인화 및 동적 콘텐츠

- 고객의 로열티 상태에 따라 다른 콘텐츠를 표시하는 메시지를 만드십시오. 만약 그들의 로열티 상태를 모른다면, 대체 메시지를 보내세요.
- 사용자의 좋아하는 제품과 마지막 구매 날짜를 포함하는 동적 메시지를 작성하십시오. 마지막 구매가 없으면 메시지를 중단하십시오.
- Liquid을 작성하여 누군가가 내 메시지를 클릭하도록 격려하는 내용을 포함하고, 남은 시간을 카운트다운으로 표시합니다. 제안이 만료된 경우, 메시지를 중단하십시오.
- 도움이 필요합니다. 사용자가 다시 돌아와서 장바구니에 남아 있는 항목이 있는지 확인하도록 메시지를 작성해 주세요.
- 고객의 국가를 기반으로 메시지를 개인화하기 위해 Liquid을 작성하십시오. 나는 국가의 이름으로 메시지를 채우고 싶다. 만약 둘 중 하나라도 없다면, 링크를 클릭하여 프로필을 업데이트하도록 제안하세요.
- 환영 메시지를 사용자의 이름으로 개인화하고 사용자의 성별에 따라 다른 문구를 작성하려면 어떻게 해야 하나요?
- 커스텀 속성, “커스텀_속성_이름“ 및 해당 값에 따라 다른 메시지를 표시하려면 Liquid을(를) 작성하십시오. 여섯 가지 다른 옵션을 보낼 수 있습니다. 커스텀 속성에 값이 없으면 입력 안내 메시지를 보내고 싶습니다.

### 특정 사용 사례

- 마케팅 캠페인에서 참여와 전환율을 높이기 위해 Liquid가 어떻게 사용되는지 몇 가지 예를 들어 줄 수 있나요?
- Liquid를 여름 세일 문자 메시지에서 유기한 장바구니 알림이나 개인화된 프로모션과 같은 경우에 어떻게 사용할 수 있나요?

피드백 세션[}을 예약하여 흥미로운 프롬프트나 경험이 있었는지 알려주세요.](https://research.rallyuxr.com/braze/schedule/clxxhw8em0d071ak4b279553s?channel=share)