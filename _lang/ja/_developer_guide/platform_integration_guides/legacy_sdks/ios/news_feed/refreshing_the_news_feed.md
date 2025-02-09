---
nav_title: フィードの更新
article_title: iOS のニュースフィードを更新する
platform: iOS
page_order: 6
description: "この参照記事では、iOS アプリケーションでニュースフィードを更新する方法について説明します。"
channel:
  - news feed

noindex: true
---

{% multi_lang_include deprecations/objective-c.md %}

# ニュースフィードの更新

{% alert note %}
ニュースフィードは非推奨になります。Braze では、News Feed ツールを使用するお客様は、コンテンツカードメッセージングチャネルに移動することを推奨しています。これは、より柔軟でカスタマイズ可能で、信頼性が高いチャネルです。詳しくは[マイグレーションガイド]({{site.baseurl}}/user_guide/message_building_by_channel/content_cards/migrating_from_news_feed/)をご覧ください。
{% endalert %}

`- (void) requestFeedRefresh;` を使用して、`Appboy.h` のユーザーのニュースフィードを更新するよう Braze に手動で要求できます。以下はその例です。

{% tabs %}
{% tab OBJECTIVE-C %}

```objc
[[Appboy sharedInstance] requestFeedRefresh];
```

{% endtab %}
{% tab swift %}

```swift
Appboy.sharedInstance()?.requestFeedRefresh()
```

{% endtab %}
{% endtabs %}

詳しくは、`Appboy.h` [ヘッダーファイル](https://github.com/Appboy/appboy-ios-sdk/blob/master/AppboyKit/include/Appboy.h "Appboy.h ヘッダーファイル") を参照のこと。


