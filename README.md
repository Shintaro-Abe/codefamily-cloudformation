# codefamily-cloudformation
## Refferemce article
Zennに投稿した、「CodePipelineとCloudformationで、API Gatewayをビルド【CodeFamily Practices 5/7】」に掲載したコードを収録したリポジトリ。
## Summary
API GatewayとLambdaの挙動を確認するための、シンプルな構成。

* ソースステージをCodeCommit、ビルドステージをCodeBuildに設定したCodePipelineを構築。
* ビルドはCloudeFormation(SAM)を使用。
* API Gatewayへメールのタイトルと本文を指定してアクセスをすると、SNSトピックのサブスクリプションへメールを送信
* 送信に成功すると、サブジェクトとメッセージの値をレスポンス。

![](/images/codefamily_cloudformation/api-cf.drawio.png =500x)

* __コマンド__

```
curl -v -X POST \
'https://Your-domain-name' \
-d $'{"sub": "テスト", "mes": "動作異常なし。"}'
```
__メール__

![](/images/codefamily_cloudformation/apicf16.png =500x)
