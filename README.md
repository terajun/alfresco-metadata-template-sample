# alfresco-metadata-template-sample
[第28回Alfresco勉強会 メタデータテンプレート](http://www.slideshare.net/terajun/28alfresco)で紹介したメタデータテンプレートのサンプルコードです。

## 使い方
サンプルコードをもとに自分でも色々試してみたい方はAlfresco SDKを使う方法がオススメです。

### 既存のAlfrescoにデプロイして使う場合
src以下にある各ファイルを以下のとおりデプロイしてAlfresco Shareを起動。

* share-config-custom.xml  
→ tomcat/shared/alfresco/web-extension/share-config-custom.xml

* custom-slingshot-documentlibrary-context.xml  
→ tomcat/shared/alfresco/web-extension/custom-slingshot-documentlibrary-context.xml

* custom-slingshot-application-context.xml  
→ tomcat/shared/alfresco/web-extension/custom-slingshot-application-context.xml

* custom_label.properties  
→ tomcat/shared/alfresco/web-extension/messages/custom_label.properties

* custom_label_ja.properties  
→ tomcat/shared/alfresco/web-extension/messages/custom_label_ja.properties

### Alfresco SDK 2.0+を使う場合
リポジトリを適当なディレクトリにクローンしてrun.batまたはrun.shを実行（手元の環境がMacなのでrun.batの動作確認はしていません。以下はMacやLinuxの場合のコマンド例）。

    $ git clone https://github.com/terajun/alfresco-metadata-template-sample.git
    $ cd alfresco-metadata-template-sample
    $ ./run.sh

Alfresco SDK 2.0+の使い方については[第26回Alfresco勉強会 Alfresco SDK + Eclipseで開発してみよう](http://www.slideshare.net/terajun/alfresco26-alfresco-sdk)を参照。

## サンプルコードについて
サンプルコードは勉強会でご紹介した3種類を用意しています。

### EXIFアスペクトをもつコンテンツにEXIF情報を表示するサンプル
デフォルト。上記の使い方に書いてあるとおり使えば適用されます。

### WorkingCopy対応のためメタデータテンプレート全体を上書き
以下のとおりリネームして、share-config-custom.xml.replaceの設定を適用して使ってください。

* share-config-custom.xml  
→ 適当な名前にリネーム

* share-config-custom.xml.replace  
→ share-config-custom.xmlにリネーム

### WorkingCopy対応のためisWorkingCopyのメタデータテンプレートを上書き
以下のとおりリネームして、share-confg-custom.xml.overrideとcustom-slingshot-documentlibrary-context.xml.overrideの設定を適用して使ってください。

* share-config-custom.xml  
→ 適当な名前にリネーム

* share-config-custom.xml.override  
→ share-config-custom.xmlにリネーム

* slingshot-documentlibrary-context.xml  
→ 末尾が「.xml」ではない名前にリネーム

* slingshot-documentlibrary-context.xml.override  
→ slingshot-documentlibrary-context.xmlにリネーム
