---
nav_title: よくある質問
article_title: 位置情報とジオフェンスのよくある質問
page_order: 4
page_type: FAQ
description: "この参考記事では、位置情報の追跡とジオフェンスの使用に関してよく寄せられる質問について説明します。"
tool: Location

---

# よくある質問

> このページでは、位置情報とジオフェンスに関してよく寄せられる質問に対する回答を示します。

## 位置情報の追跡

### Braze はいつ位置データを収集しますか?

Braze は、アプリケーションがフォアグラウンドで開いている場合にのみ位置情報を収集します。その結果、フィルター `Most Recent Location` は、ユーザーが最後にアプリケーションを開いた位置情報 (セッション開始とも呼ばれます) に基づいてユーザーをターゲットにします。

また、次のニュアンスにも留意する必要があります。

- 位置情報が無効になっている場合、`Most Recent Location` フィルターは最後に記録された位置情報を表示します。
- ユーザーがプロフィールに位置情報を保存したことがある場合は、それ以降に位置情報の追跡をオプトアウトした場合でも、`Location Available` フィルターの対象となります。

### 「最新のデバイスロケール」フィルターと「最新の位置情報」フィルターの違いは？

`Most Recent Device Locale` はユーザーのデバイス設定から取得されます。例えば、iPhone の場合は、デバイスの [**設定**] > [**一般**] > [**言語と地域**] に表示されます。このフィルターは、日付や住所などの言語や地域の書式をキャプチャするために使用され、`Most Recent Location` フィルターとは無関係です。

`Most Recent Location` は、デバイスの最新の既知の GPS 位置です。これはセッション開始時に更新され、ユーザーのプロファイルに保存されます。

### ユーザーが位置情報の追跡をオプトアウトした場合、古い位置データは Braze から削除されますか? 

いいえ。ユーザーがプロフィールに位置情報を保存したことがある場合、後で位置情報の追跡をオプトアウトしても、そのデータは自動的に削除されません。

## ジオフェンス

### ジオフェンスと位置情報の追跡の違いは？

Braze では、ジオフェンスは位置情報の追跡とは概念が異なります。ジオフェンスは特定のアクションのトリガーとして使用されます。ジオフェンスは、地理的位置の周囲に設定された仮想境界です。ユーザーがこの境界に出入りすると、メッセージの送信など特定のアクションをトリガーできます。

位置追跡は、ユーザーの最新の位置データを収集して保存するために使用されます。このデータを使用して、フィルターに基づいて `Most Recent Location` ユーザーをセグメント化できます。例えば、`Most Recent Location` フィルターを使用して、ニューヨークにいるユーザーにメッセージを送信するなど、オーディエンスの特定の地域をターゲットにすることができます。

### Braze のジオフェンスはどのくらい正確ですか?

Braze のジオフェンスは、デバイスで使用可能な位置情報のすべてのプロバイダーの組み合わせを使用して、ユーザーの位置を三角測量で割り出します。これには、WiFi、GPS、携帯電話の電波塔などが含まれます。

標準精度は 20～50m の範囲で、ベストケースの精度は 5～10m の範囲です。地方では、精度が大幅に低下し、数キロメートルに達する可能性があります。Braze は、地方では半径の大きいジオフェンスを作成することを推奨しています。

ジオフェンスの精度に関する詳細については、[Android](https://developer.android.com/develop/sensors-and-location/location/geofencing)および[iOS](https://developer.apple.com/library/archive/documentation/UserExperience/Conceptual/LocationAwarenessPG/RegionMonitoring/RegionMonitoring.html#//apple_ref/doc/uid/TP40009497-CH9-SW1)のドキュメントを参照してください。

### ジオフェンスはバッテリーの駆動時間にどのように影響しますか? 

当社のジオフェンシングソリューションは、iOS と Android のネイティブジオフェンスシステムサービスを使用し、精度と電力をインテリジェントにトレードオフするよう調整されており、基盤となるサービスの向上に伴い、クラス最高のバッテリー駆動時間とパフォーマンスを向上しています。

### ジオフェンスはいつアクティブになりますか?

Braze のジオフェンスは、アプリを閉じていても 1 日中いつでも機能します。これらは、定義され、Brazeダッシュボードにアップロードされるとすぐにアクティブになります。ただし、ユーザーが位置の追跡を無効にしている場合、ジオフェンスは機能しません。

ジオフェンスを機能させるには、ユーザーのデバイスで位置情報サービスを有効にし、位置情報にアクセスする権限をアプリに付与する必要があります。ユーザーが位置追跡を無効にしている場合、アプリはユーザーがジオフェンスに出入りするタイミングを検出できません。

### ジオフェンスデータはユーザープロファイルに保存されますか? 

いいえ、Braze はジオフェンスデータをユーザープロファイルに保存しません。ジオフェンスは Apple と Google の位置情報サービスによって監視されており、Braze はユーザーがジオフェンスをトリガーした場合にのみ通知を受け取ります。その時点で、関連するトリガーキャンペーンが処理されます。

### ジオフェンス内にジオフェンスを設定できますか?

ベストプラクティスとして、ジオフェンスを相互に設定することは避けてください。通知のトリガーで問題が発生する可能性があります。

[3]: https://developers.google.com/android/reference/com/google/android/gms/location/package-summary
[4]: https://developer.apple.com/library/content/documentation/UserExperience/Conceptual/LocationAwarenessPG/RegionMonitoring/RegionMonitoring.html
