# Teamstudio Adviser の使い方

Teamstudio Adviser は HCL Notes/Domino 環境内のアプリケーションすべてを調査するための情報群を収集します。これには次の 4つのモジュールがあります:  「カタログ」、「利用状況」、「複雑さ」、そして 「ガイダンス」です。

## 「カタログ」
このカタログ収集モジュールは、Domino サーバー群のカタログから情報を読み取り、データベースとテンプレートの一覧を提供します。カタログ情報は、データベースの名前別、サーバー別、テンプレートのみ、最近修正があったものなど様々な切り口で確認できます。カタログから収集した情報に加えて、このモジュールではそれぞれのデータベースにビジネス上の価値を1 から 5 まで設定でき、ビジネス上の重要度の観点からも追跡可能です。情報のノイズを少なくするため、他の Adviser モジュール群から特定のデータベースを除外できるフィルター機能も構成できます。

詳細は次のカタログモジュール内の[文書](catalog.md)をご参照ください。

## 「利用状況」
この利用状況収集モジュールは、Domino サーバーのログから情報を読み込み、ユーザーとデータベースの両方の詳細な利用状況統計を表示します。データベースに対しては、誰に何回アクセスされたかが確認でき、加えて利用状況が増加または現象しているかを示す過去からのトレンドも確認できます。ユーザーに対しては、あるユーザーがアクセスしたデータベースとサーバーのすべてを確認できます。

詳細は次の利用状況モジュール内の[文書](usage.md)をご参照ください。

## 「複雑さ」
複雑さ収集モジュールは、サーバー上で配置されているデータベースもれなくスキャンし、その設計の複雑さのスコアを生成します。アプリケーションの移行や移植がどの程度難しいかを判定します。このスコアは、例えば設計のサイズや設計要素の異なるタイプの数、移行が困難となる Domino 特有の機能のカウントなど数多くの要因に基づき生成されます。独自の環境下で仮にこれがあると移行が難しくなるといったコードや定数をキーワードとして指定することもできます。キーワードの例として、内部システムで使用される第三者の知的所有物や DLL 内で外部システムへの参照など、環境に合わせて設定いただけます。

詳細は複雑さモジュール内の[文書](complexity.md)をご参照ください。

## 「ガイダンス」
ガイダンスモジュールは上記のモジュールから収集された情報を集約し、それぞれのデータベースを整理し将来の道筋を提案します。この提案は、アプリケーションの利用状況、設計の複雑さ、ビジネス上の価値の組み合わせを基に行われます。この提案に関わらず、特定のデータベースにはすでに計画や処遇が決定されている場合には、ユーザーがこの提案を書き換え可能です。

詳細はガイダンスモジュール内の[文書](guidance.md)をご参照ください。