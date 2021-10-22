# Show my report without downloading (WebClass)

## これは何？

埼玉大学生向けChrome拡張機能。

WebClassを使う際、 `（科目）→「マイレポート」→（ファイル名）` とすることで提出したレポートを見ることができます。<br>
しかし、閲覧するためにはダウンロードする必要があります。<br>
この拡張機能を用いると、ダウンロードすることなくファイルを閲覧することができます。

## 仕組み（開発者向け）

`webclass.gks.saitama-u.ac.jp` ドメイン内部において、 `Content-Disposition` ヘッダが含まれていれば、そのヘッダを削除するだけです。

このヘッダは、`Content-Disposition: attachment` とすることで、ダウンロードすべきであることを示します。<br>
このヘッダを削除すると、既定値である `inline` となり、ウェブページとして表示可能となります。<br>
詳しくは [Content-Disposition - HTTP | MDN](https://developer.mozilla.org/ja/docs/Web/HTTP/Headers/Content-Disposition) をご確認ください。

## ライセンス
MIT License