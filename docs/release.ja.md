# リリースノート

## Teamstudio Adviser 6.7.0 - リリースノート
現在の最新バージョン、Adviser 6.7.0 は Teamstudio Adviser の機能拡張版です。下の不具合修正リストをご参照ください。インストール前に、インストールガイド([こちら](installing.md)) を注意してお読みください。

## Adviser 6.7 での主な新機能
### フィルターでディレクトリーをサポート
選択したデータベースの親ディレクトリは、[フィルタ] ボタンのドロップダウンを使用してフィルタリングできるようになり、現在のサーバー上またはすべてのサーバー上のディレクトリ内のすべてのデータベースにフィルタを適用できます。フィルタリングの詳細については、[フィルター機能](filters.md)のセクションを参照してください。

### フィルターをかけたデータベースに対する複雑さ分析の除外
データベースをフィルタリングすると、複雑さスキャンではフィルタリングされたデータベースの複雑性情報を作成/更新しなくなります。 ディレクトリーのフィルタリングと組み合わせることで、初期スキャン時のパフォーマンスを大幅に向上させることができます。この操作は有害に働くものではなく、複雑さのデータは破棄されることはありません。古くなった複雑さの情報は UI 上でフラグが立てられ、フィルタを削除することで、将来のスキャンで複雑さを再度更新できるようになっています。

### ログ UI に対する改善
ブラウザアプリのログペインは、エラーメッセージをクリックしたときにスタックトレースを表示したり、タイムゾーン間でより正確な日付ごとのグループ化を表示したり、ログエントリ内のテキストのコピーができるように改善しました。

## Upgrading
### 直前のバージョン Adviser 6 からのアップグレード 
Adviser のアップグレードは、サーバー用データベースの設計を再設計または設計の置換を行う必要があります。そして、Adviser ワークステーションとして動作する Notes クライアントとサーバーの HTTP タスクの両方を再始動する必要があります。詳細のステップは [インストール方法](installing.md) の Adviser のアップグレード を参照してください。

### Usage Auditor 5.x からのアップグレード
Usage Auditor 5.0 からアップグレードし、それまでに収集したすべての利用状況データを保持することができます。ただし、Usage Auditor の  5.0 より前のバージョンで収集したデータは Adviser に取り込むことはできません。アップグレードでご不明の点がありましたら技術サーポートにご連絡ください。

### Adviser と Usage Auditor 5.x の並列運用
Adviser を試用中は、Adviser と Usage Auditor の並行運用が考えられます。サポートしていますが、それぞれは別々のワークステーションで実行する必要があります。Adviser ワークステーションデータベースには長時間にわたって実行するスケジュールエージェントがあり、サーバーで要求のあったジョブを検知を行います。このエージェントは Usage Auditor のエージェント起動を許可しません。

## 既知の問題
* Adviser が利用状況データを更新する時、HSQL からのエラーメッセージがサーバーログに記録されます。このメッセージは良性で、Domino の JVM ポリシーによって HSQL がロギングレベルを調整できないことに言及するものです。メッセージは次のようになります  
  &lt;clinit&gt; failure initializing JDK logging system.  Continuing without Application logging.  
  HTTP JVM: java.security.AccessControlException: Access denied (java.util.logging.LoggingPermission control)
* ブラウザの「パスワードの保存」はいくつかのブラウザあるいはプラットフォーム上でブラウザUIにエラーを発生させる可能性があります。詳しくは [インストール方法](installing.md)のブラウザとパスワード保存を参照してください。
* 複雑さスキャンの実行中、プロセスに使用する ID の再利用の関係で Adviser ワークステーションに「Notes initialization failed」という警告をログ出力する場合があります。通常、この類の警告は動作そのものには支障はなく、ワークステーションはリカバーし処理を継続しています。

## 不具合修正
### Adviser 6.7.0
[TMS-1423] - フレームワーク対応の Web UI をアップグレード  
[TMS-1424] - フィルタリングしたデータベースの複雑さ分析をスキップ  
[TMS-1425] - データベースの親ディレクトリのフィルタリングを可能に  
[TMS-1426] - Web UI のログ表示を改善し、テキストの選択やスタックトレースの表示/選択が容易になるようにしました  
[TMS-1427] - ローカルタイムゾーンに関する Web UI ログビューの日付グループ化の精度を向上させました  
[TMS-1429] - 文書が再ロードされるまでデータベースの詳細にあるビジネスバリューが「固定」されていた問題を修正
