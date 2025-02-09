---
nav_title: SDK によるデータ収集
article_title: SDK によるデータ収集
page_order: 1
page_type: reference
description: "このリファレンス記事では、パーソナライズされた連携、自動的に収集される連携、および最小限の連携を通じて SDK によって収集されるデータについて説明します。"

---

# SDK によるデータ収集

> Braze SDK をお客様のアプリやサイトと連携すると、Braze は特定タイプのデータを自動的に収集します。これらのデータの一部は、私たちのプロセスにとって不可欠なものであり、これらのデータの一部は、あなたのニーズに基づいてオンまたはオフにすることができる。セグメンテーションやメッセージングをさらに強化するために、Brazeを設定して追加タイプのデータを収集することもできる。

Brazeは柔軟なデータ収集ができるように設計されているため、Braze SDKを以下の方法で統合することができる：

- **[最低限の統合](#minimum-integration)：**Brazeは、Brazeのサービスと通信するために必要なデータを自動的に収集する。
- **[デフォルトで収集されるオプションデータ](#optional-data-collected-by-default)：**Brazeは、ほとんどのユースケースで幅広く役立つデータを自動的に取得する。Brazeサービスとのコミュニケーションに必要でない場合は、このデータの自動収集を無効にすることができる。
- **[デフォルトでは収集されないオプションデータ](#data-not-collected-by-default)：**Brazeは、特定のユースケースに有用な一部のデータを収集し、広範なコンプライアンス上の理由から自動的に収集をイネーブルメントにしない。このデータ収集は、ユースケースに合わせて選択することができる。
- **[パーソナライズされた統合](#personalized-integration)：**Brazeでは、デフォルトのオプションデータに加えて、柔軟にデータを収集することができる。

## 最小限の連携

SDK初期化時にBrazeが生成・受信するデータのうち、厳密に必要なものを以下に示す。このデータはコンフィギュレーション不可能で、プラットフォームのコア機能に不可欠である。セッション開始とセッション終了を除き、他のすべての自動トラッキングデータは、データポイントの割り当てにカウントされない。

| 属性 | 説明 | なぜ収集されるのか |
| --------- | ----------- | ------------------ |
| アプリのバージョン名 / <br> アプリのバージョンコード | アプリの最新バージョン | この属性は、アプリのバージョン互換性に関連するメッセージを適切なデバイスに送信するために使用される。サービスの中断やバグをユーザーに通知するために使用できる。 |
| 国 | IPアドレスのジオロケーションによって識別される国 | この属性は、位置に基づいてメッセージをターゲット化するために使用される。 |
| デバイス ID | デバイス識別子、ランダムに生成される文字列 | この属性は、ユーザーのデバイスを区別し、正しいデバイスにメッセージを送信するために使用される。 |
| OS と OS バージョン | 現在レポートされているデバイスまたはブラウザと、デバイスまたはブラウザのバージョン | この属性は、互換性のあるデバイスにのみメッセージを送信するために使用される。また、アプリのバージョンをアップグレードするユーザーをターゲットとするセグメンテーションにも使用できます。 |
| セッション開始とセッション終了 | ユーザーが統合されたアプリやサイトを使い始めるとき | Braze SDK では、ユーザーエンゲージメントやユーザーの理解に不可欠なその他の分析を計算するため、Braze ダッシュボードで使用されるセッションデータがレポートされます。アプリやサイトからセッション開始とセッション終了が呼び出される正確なタイミングは、開発者が設定できる[（Android]({{site.baseurl}}/developer_guide/platform_integration_guides/android/analytics/tracking_sessions/)、[iOS]({{site.baseurl}}/developer_guide/platform_integration_guides/swift/analytics/tracking_sessions/)、[Web]({{site.baseurl}}/developer_guide/platform_integration_guides/web/analytics/tracking_sessions/)）。 |
| SDKメッセージ・インタラクション・データ | プッシュ直接開封数、アプリ内メッセージインタラクション数、コンテンツカードインタラクション数 | この属性は、メッセージが受信され、送信が重複していないことの確認など、品質管理の目的で使用されます。 |
| SDKバージョン | 現在のSDKバージョン | この属性は、互換性のあるデバイスにのみメッセージを送信し、サービスの中断を避けるために使用される。 |
| セッションIDとセッションタイムスタンプ | セッション識別子、ランダムに生成された文字列とセッションのタイムスタンプ。 | ユーザが新しいセッションを開始しているか、既存のセッションを開始しているかを判断し、このユーザ宛てのメッセージの再有効性を判断するために使用される。<br><br>アプリ内メッセージやコンテンツカードなどの特定のメッセージングチャネルは、セッションの開始時にデバイスに同期されます。そして、私たちのバックエンドは、最後にBrazeサーバーにコンタクトしたときに関連するデータ（デバイスが保存して送り返す）を使って、ユーザーが新しいメッセージを受け取る資格があるかどうかを知る。|
{: .reset-td-br-1 .reset-td-br-2 .reset-td-br-3  .reset-td-br-4 role="presentation" }

### 計算された指標

Brazeは、SDKデータ、SDK以外のメッセージに関連するメッセージインタラクションデータ、および派生情報から計算されたメトリクスを生成する。わかりやすく言うと、この計算されたデータは SDK が追跡するものではなく、Braze サービスによって生成されるデータであり、ユーザープロファイルには追跡されたデータと生成されたデータの両方が表示されます。 

計算された指標には、次の属性が含まれます。

| 属性                                      | 説明                                                          |
|-----------------------------------------------|----------------------------------------------------------------------|
| 最初に使用したアプリ                                 | 時刻                                                                 |
| 最後に使用したアプリ                                  | 時刻                                                                 |
| 総セッション数                            | 数値                                                               |
| クリックされたカード                                   | 数値                                                               |
| 最後に受信したメッセージ                     | 時刻                                                                 |
| 最終受信メールキャンペーン                   | 時刻                                                                 |
| 最後に受信したプッシュキャンペーン                    | 時刻                                                                 |
| フィードバック項目の数                       | 数値                                                               |
| 直近Y日間のセッション数          | 番号と時間                                                      |
| キャンペーンからメッセージを受信                  | ブール値。このフィルターは、過去のキャンペーンを受けたかどうかに基づいてユーザー群をターゲットにする。                               |
| タグの付いたキャンペーンからのメッセージを受け取った        | ブール値。このフィルターは、現在タグを持つキャンペーンを受け取ったかどうかに基づいてユーザー群をターゲットにする。                  |
| リターゲットキャンペーン                              | ブール値。このフィルターは、過去に特定のメール、プッシュ、アプリ内メッセージを開封またはクリックしたかどうかに基づいてユーザー群をターゲットにする。 |
| アンインストール                                    | ブール値と時間 |
{: .reset-td-br-1 .reset-td-br-2 .reset-td-br-3  .reset-td-br-4 role="presentation" }

{% alert important %}
最低限の統合にしか興味がなく、mParticle、セグメンテーション、Tealium、またはGTMと統合する場合は、以下の点に注意すること：
- **モバイルプラットフォーム**：mParticleとセグメンテーションは、プラットフォームを通じてこれを行う方法を提供していない。 
- **Web**: 最小限の連携構成を可能にするために、Braze の連携をネイティブに行う必要があります。タグマネージャーはプラットフォームを通じてこれを行う方法を提供していない。
{% endalert %} 

## デフォルトで収集されるオプションのデータ

最小限の統合データに加えて、SDK統合を初期化する際に以下の属性がBrazeによって自動的に取り込まれる。最小限の統合を可能にするために、これらの属性の収集を[オプトアウトする]({{site.baseurl}}/developer_guide/platform_integration_guides/sdk_primer/#blocking-data-collection)ことができる。

| 属性               | プラットフォーム          | 説明                                                                        | なぜ収集されるのか                                                                                                                                                      |
|-------------------------|-------------------|------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ブラウザ名            | Web               | ブラウザ名                                                                | この属性は、互換性のあるブラウザにのみメッセージを送信するために使用される。また、ブラウザベースのセグメンテーションにも使用できる。                                     |
| デバイスロケール           | Android、iOS      | デバイスのデフォルトロケール                                                   | この属性は、メッセージをユーザーの好みの言語に翻訳するために使われる。                                                                                            |
| デバイスモデル            | Android、iOS      | 機器固有のハードウェア                                                | この属性は、互換性のあるデバイスにのみメッセージを送信するために使用される。また、セグメンテーション内でも使用できます。                                                 |
| デバイスブランド            | Android           | デバイスのブランド (例: Samsung)                                         | この属性は、互換性のあるデバイスにのみメッセージを送信するために使用される。                                                                                          |
| デバイスの通信事業者 | Android、iOS      | 携帯キャリア                                                                 | この属性は、オプションでメッセージのターゲティングに使われる。<br><br>**注:**このフィールドはiOS 16で非推奨となり、将来のiOSバージョンではデフォルトで`--` 。 |
| 言語                | Android、iOS、Web | デバイスまたはブラウザの言語                                                            | この属性は、メッセージをユーザーの好みの言語に翻訳するために使われる。                                                                                            |
| 通知設定   | Android、iOS、Web | このアプリがプッシュ通知を有効にしているかどうか。                                   | この属性は、プッシュ通知を有効にするために使用される。                                                                                                                    |
| 解像度              | Android、iOS、Web | デバイスまたはブラウザの解像度                                                          | オプションで、デバイスベースのメッセージターゲティングに使用される。この値のフォーマットは "`<width>`x`<height>`" である。                                                                 |
| タイムゾーン               | Android、iOS、Web | デバイスまたはブラウザのタイムゾーン                                                           | この属性は、各ユーザーのローカルタイムゾーンに従って、適切な時間にメッセージを送信するために使用される。                                                   |
| ユーザーエージェント              | Web               | [ユーザーエージェント](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent) | この属性は、互換性のあるデバイスにのみメッセージを送信するために使用される。また、セグメンテーション内でも使用できます。                                                 |
{: .reset-td-br-1 .reset-td-br-2 .reset-td-br-3  .reset-td-br-4 role="presentation" }

デバイスレベルプロパティ（デバイスのワイヤレスキャリア、タイムゾーン、解像度など）のトラッキングの詳細については、プラットフォーム固有のドキュメントを参照のこと：[Android]({{site.baseurl}}/developer_guide/platform_integration_guides/android/storage/ "Android の許可リストのドキュメント")、[iOS]({{site.baseurl}}/developer_guide/platform_integration_guides/swift/storage/ "iOS の許可リストのドキュメント")、[Web]({{site.baseurl}}/developer_guide/platform_integration_guides/web/cookies_and_storage/#device-properties "Web の許可リストのドキュメント")。

## デフォルトでは収集されないデータ

デフォルトでは、以下の属性は収集されない。それぞれの属性を手動で統合する必要がある。

| 属性                  | プラットフォーム     | 説明                                                                                                                                                                                                                                                                                                               | 収集されない理由                                                                                                                                                                                                                                                                 |
|----------------------------|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| デバイス広告のトラッキングを有効にする | Android、iOS | iOSの場合：<br>[`set(adTrackingEnabled:)`](https://braze-inc.github.io/braze-swift-sdk/documentation/brazekit/braze/set(adtrackingenabled:))<br><br> Android の場合: <br>[`Braze.setGoogleAdvertisingId()`](https://braze-inc.github.io/braze-android-sdk/kdoc/braze-android-sdk/com.braze/-i-braze/set-google-advertising-id.html) | このプロパティには、追加のアプリケーションレベルの権限が必要です。この権限は、インテグレータによって付与される必要があります。                                                                                                                                                                                      |
| デバイス IDFA                | iOS          | 広告主のデバイス識別子                                                                                                                                                                                                                                                                                         | これにはAd Tracking Transparencyフレームワークが必要で、App Storeによる追加のプライバシー審査が行われる。詳細は以下を参照のこと。 [`set(identifierForAdvertiser:)`](https://braze-inc.github.io/braze-swift-sdk/documentation/brazekit/braze/set(identifierforadvertiser:)) |
| Google 広告 ID      | Android      | Google Playアプリ内の広告用識別子                                                                                                                                                                                                                                                                        | これには、アプリが GAID を取得して Braze に渡す必要があります。詳細については、「[Google広告IDのオプション]({{site.baseurl}}/developer_guide/platform_integration_guides/android/initial_sdk_setup/optional_gaid_collection)」を参照のこと。                                         |
{: .reset-td-br-1 .reset-td-br-2 .reset-td-br-3  .reset-td-br-4 role="presentation" }

## パーソナライズされた連携

Brazeを最大限に活用するために、私たちのSDKインテグレーターは、Braze SDKを実装し、自動収集されたデータに加え、ビジネスに関連する[カスタム属性]({{site.baseurl}}/user_guide/data_and_analytics/custom_data/custom_attributes/#setting-custom-attributes)、[カスタムイベント]({{site.baseurl}}/user_guide/data_and_analytics/custom_data/custom_events/#logging-custom-events)、[購入イベントを]({{site.baseurl}}/user_guide/data_and_analytics/custom_data/purchase_events/#logging-purchase-events)ログに記録することがよくあります。

パーソナライズされた連携により、ユーザーエクスペリエンスに関連付けてコミュニケーションをカスタマイズできます。

{% alert important %}
Brazeは、5,000,000セッションを超えるユーザー（「ダミーユーザー」）を禁止またはブロックし、SDKイベントを取り込まなくなる。詳細については、「[スパムのブロック]({{site.baseurl}}/user_guide/data_and_analytics/user_data_collection/user_archival/#spam-blocking)」を参照してください。
{% endalert %}


[1]: https://braze-inc.github.io/braze-android-sdk/kdoc/braze-android-sdk/com.braze.enums/-device-key/index.html "Android のデバイスレベルのフィールド"
