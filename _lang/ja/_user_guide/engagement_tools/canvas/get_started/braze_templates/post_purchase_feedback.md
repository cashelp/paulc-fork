---
nav_title: 購入後のフィードバック
article_title: 購入後のフィードバック
page_order: 6
page_type: reference
description: "この記事では、Brazeキャンバステンプレートを使ってパーソナライズされた体験をオーケストレーションし、フィードバックに対応したりユーザーとの関係を構築したりする方法について説明する。"
tool: Canvas
---

# 購入後のフィードバック

> 購入後のフィードバックテンプレートを使って、カスタマーエクスペリエンスに関する重要なインサイトを獲得し、カスタマーエクスペリエンスを継続させよう。パーソナライズされたコミュニケーションと体系化されたメッセージを活用することで、顧客との関係を構築し、育み続けることができる。

この記事では、ユーザーライフサイクルのコンバージョンステップ用にデザインされた「**購入後フィードバック」**テンプレートのユースケースを紹介する。完成すれば、ユーザーにアプリへのフィードバックを提供するよう促すキャンバスができあがる。

## 前提条件

このテンプレートをうまく使うには、以下のものが必要だ：

- フィードバックアンケートの結果を参照するための[カスタム属性]({{site.baseurl}}/user_guide/data_and_analytics/custom_data/custom_attributes/#managing-custom-attributes)。
- 設定された[Braze Audience Syncと]({{site.baseurl}}/partners/canvas_steps)、使用しているパートナーやオーディエンス。

## テンプレートをニーズに合わせる

例えば、我々がモバイルゲーム開発者であるDecorumsoft社で働いているとしよう。購入後のフィードバック・テンプレートを使って、最新発売の動画ゲーム『Proxy War 3』のフィードバックを測定する：喉の渇きとの戦いだ。このフィードバックをもとに、拡張パック『リキッドミラージュ』の開発計画を進めていく。

キャンバスを作成する前に、[Braze Audience Sync to Google]({{site.baseurl}}/partners/canvas_steps/google_audience_sync/)インテグレーションを設定し、BrazeのユーザーデータをGoogle Audiencesに追加して、行動トリガーやセグメンテーションなどに基づいて広告を送信できるようにした。

購入後のフィードバックテンプレートにアクセスするには、新しいキャンバスを作成する際に、「**キャンバステンプレートを使用する**」＞「**Brazeテンプレート**」を選択する。次に、「**購入後フィードバック**」の横にある「**テンプレートを適用**」を選択する。あとは、テンプレートを見ながら、自分たちのニーズに合わせていくだけだ。

### ステップ 1: キャンバスの詳細を設定する

キャンバスの詳細を調整して、我々の目標を反映させよう。

1. テンプレート名の横にある**Editを**選択する。

![]({% image_buster /assets/img/canvas_templates/post_purchase_feedback/select_edit_details.png %}) キャンバスの現在のタイトルと説明。{: style="max-width:50%;"}

{:start="2"}
2\.キャンバス名を更新し、キャンバスが最近のユーザーをターゲットにしたものであることを指定する。
3\.説明文を更新し、キャンバスがユーザーからのフィードバック提出を促すためのものであることを明記する。
4. キャンバスのホームページでフィルターをかけるために、タグ「**フィードバック**」を追加する。

![キャンバスの新しい名前と説明。新しい記述にはこうある：PWD3の次期拡張「Liquid Mirage」への関心を測るための、購入後のフィードバックキャンバス」]({% image_buster /assets/img/canvas_templates/post_purchase_feedback/enter_new_canvas_name.png %}){: style="max-width:50%;"}

### ステップ2:コンバージョンイベントを割り当てる

次に、コンバージョンイベントを割り当てよう。**1次コンバージョンイベント-Aを**「**Make specific purchase**」に更新し、「**Proxy War**」を選択する。

![代理戦争ゲーム商品購入のコンバージョンイベントタイプの「コンバージョンイベントの割り当て」セクション]({% image_buster /assets/img/canvas_templates/post_purchase_feedback/select_conversion_event.png %}){: style="max-width:90%;"}

テンプレートのコンバージョン期限を3日にしておくのは、直近のユーザーをターゲットにしたいからだ。

### ステップ 3:エントリーのスケジュールを設定する

1. エントリーのスケジュールタイプを**アクションベースにして**おく。
2. エントリーウィンドウの**Start Timeを**ゲーム開始日に設定する。

### ステップ4:キャンバスに入る人を決める

フィードバックの対象は、Proxy War 3を最近購入したユーザーだ。

1. ターゲットセグメント「Proxy War 3を購入したユーザー」を選択する。
2. プロキシー・ウォー3』を「0」回以上購入したユーザーを含めるフィルターを選択する。

![]({% image_buster /assets/img/canvas_templates/post_purchase_feedback/entry_window_segment.png %}) ゲームを購入したユーザーをセグメンテーションする「購入済み代理戦争3」という名前のセグメント。{: style="max-width:90%;"}

{: start="3"}
3\.キャンバスの最大持続時間後にユーザーがキャンバスに再入場できないようにエントリコントロールを更新する。

### ステップ 5: 送信設定を選択する

デフォルトのサブスクリプション設定を維持し、メッセージや通知の受信を申し込んだユーザーだけに送信する。 

送信には細心の注意を払いたいので、ユーザーのタイムゾーンで午後11時から午前10時の間にフィードバックをリクエストするのを避け、次に送信可能な時間帯にのみ送信するよう、**イネーブルメントを**選択する。

!["送信設定 "ステップは、サブスクライバーまたはオプトインしているユーザーを対象とする。]({% image_buster /assets/img/canvas_templates/post_purchase_feedback/send_settings_with_quiet_hours.png %}){: style="max-width:90%;"}

この例では、他の設定（フリークエンシーキャップとシードグループ）は省略する。

### ステップ 6:キャンバスをカスタマイズする

次に、メッセージングチャネルとユーザーに送信するコンテンツをカスタマイズしてキャンバスを構築する。我々はメール、アプリ内メッセージ、Webhookチャネルを使ってのみフィードバックを求めているため、テンプレートを確認し、MessageステップからSMSバリアントを削除する。

各メッセージング・コンポーネントの内容を更新することからカスタマイズを始めよう。参照するカスタム属性は`Experience Feedback` である。

1. キャンバスビルダーで、ユーザージャーニーの最初のメッセージステップを選択する。
2. **メールの**バリアントを選択する。
3. **送信情報には**、ユーザーからのフィードバックを促すような件名を記入する。 
4. **メッセージの編集を**選択して、テンプレートのメールメッセージを当社のフィードバック調査メッセージに置き換える。これには、ユーザー・ジャーニーのアクション・パスのステップで参照される、どのオプションが選択されたかをキャプチャするための各コール・トゥ・アクションのリンクの置き換えも含まれる。

{% alert tip %}
[キャンバスエントリプロパティを使って]({{site.baseurl}}/user_guide/engagement_tools/canvas/create_a_canvas/canvas_entry_properties_event_properties/)、どの製品を参照しているかに応じてキャンバスのメッセージをカスタマイズすることができる。
{% endalert %}

#### フィードバック調査の設定

次に、**アプリ内メッセージの**バリアントの詳細を記入する必要がある。ここで、ユーザーフィードバックのセンチメントを示す`Experience Feedback` カスタム属性を指定する必要がある。(この後のアクションパスのステップでも参照する）。

1. 同じ最初のメッセージのステップで、**アプリ内メッセージの**バリアントを選択する。メッセージコントロールはそのままにしておく。 
2. ヘッダーと本文には、ユーザーがProxy War 3での経験を正直に語ることを促す言葉を使う。
3. アンケートの回答はプロファイルに記録されるため、アンケートは**単一選択と**し、**送信時に属性を記録する**ことにする。
4. 3つのアンケート選択肢のそれぞれについて、カスタム属性として「**カスタマーエクスペリエンス フィードバック**」を選択する。 
5. ユーザープロファイルの属性値は、カスタム属性と一致しているので、そのままにしておく。

![最近購入したProxy War 3が面白かったかどうかを3つの選択肢でユーザーに尋ねるアンケート：「]({% image_buster /assets/img/canvas_templates/post_purchase_feedback/survey_example_iam.png %}){: style="max-width:90%;"}

#### アクションパスを構築する

カスタム属性（`Experience Feedback` ）と前のセクションの属性値を使って、テンプレートのアクションパスを更新し、属性と値を一致させる。

![]({% image_buster /assets/img/canvas_templates/post_purchase_feedback/action_path_good_example.png %}) アンケートで「気に入った」と回答したユーザーを含む、アクションパスステップの「良いフィードバック」グループ。{: style="max-width:90%;"}

### リターゲティング広告を設定する

**リターゲティング広告の**ステップで、Google オーディエンス同期が設定されていることを確認する。これには、広告アカウントの選択、既存のオーディエンスの選択、ユーザーをオーディエンスに追加するオプションが含まれる。

### Webhookサポートケースの設定

次に、潜在的なサポート・ケースをトリガーするWebhookを設定しよう。これは、ユーザーフィードバックの分析と組み合わせることで、特にインサイトを得ることができる。

**サポートケースの作成という**メッセージステップでは、購入した商品に満足できず返金を希望するユーザーのために、Webhookを作成するテンプレートを更新する。

![]({% image_buster /assets/img/canvas_templates/post_purchase_feedback/webhook_example.png %}) Proxy War 3を購入した顧客で、否定的な感情を持ち、返金を希望する顧客のサポートケースを作成するWebhook。{: style="max-width:90%;"}

### ステップ 6:キャンバスをテストして起動する

キャンバスをテストし、期待通りに動作することを確認したら、**キャンバスを起動**するために「**Launch Canvas**」を選択する。これで、パーソナライズされたユーザージャーニーでユーザーをマインドフルにターゲット化し、最近Proxy War 3を購入したユーザーに基づいてフィードバック調査への回答を促すことができる！

{% alert tip %}
キャンバスを立ち上げる[前と後に]({{site.baseurl}}/user_guide/engagement_tools/canvas/ideas_and_strategies/pre_post_launch_checklist/#things-to-consider-before-launch)考慮すべきことについては、[立ち上げ前後のチェック]({{site.baseurl}}/user_guide/engagement_tools/canvas/ideas_and_strategies/pre_post_launch_checklist/#things-to-consider-before-launch)リストをチェックしよう。
{% endalert %}
