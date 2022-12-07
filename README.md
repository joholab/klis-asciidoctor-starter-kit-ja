# KLIS Asciidoctor スターターキット（日本語版）

（非公式）知識情報・図書館学類卒業論文用Asciidoctorテンプレート

[サンプルPDF](index.pdf)

## :warning: 注意事項
- 上保研究室メンバーに向けて作成した非公式版です
- 他研究室の学生は使用前に指導教員に確認してください
- 抄録は含まれていませんので、学類指定のフォーマットに従いましょう

## 環境

- [Ruby](https://rubyinstaller.org/) :bulb: バージョンは`2.x.x`の最新版を推奨（2021.12.21現在）
- [Visual Studio Code](https://azure.microsoft.com/ja-jp/products/visual-studio-code/)（VSCode）
    - [AsciiDoc拡張機能](https://marketplace.visualstudio.com/items?itemName=asciidoctor.asciidoctor-vscode)

## インストール

### Windows10/11の場合

1. Rubyをインストールする
2. Rubyに関連パッケージを追加する（以下のコマンドを`Windows PowerShell`から実行する）
```
PS C:\Users\アカウント名>gem install -N rouge asciidoctor asciidoctor-pdf
```
3. VSCodeをインストールする
4. VSCodeにAsciiDoc拡張機能を追加する

## PDFファイルの生成

- 緑色の「`<> Code`」ボタンをクリック→`Download ZIP`を選択
- ダウンロードしたファイルを展開
- 下記フォントを入手して、`fonts`フォルダに保存
    - [SourceHanSerifJP-VF.ttf](https://github.com/adobe-fonts/source-han-serif/tree/release/Variable/TTF/Subset)
    - [KaiGenGothicJP-Regular.ttf](https://github.com/chloerei/asciidoctor-pdf-cjk-kai_gen_gothic/releases)
    - [RobotoMono-VariableFont_wght.ttf](https://fonts.google.com/specimen/Roboto+Mono)（ダウンロード→展開）
- [大学ホームページ](https://www.tsukuba.ac.jp/about/outline-logomark/)から校章画像をダウンロードして、`themes`と`images`フォルダにそれぞれ保存
    - :muscle: 上級者向け：校章画像ファイルは`.gitignore`に登録されています
- ダウンロードしたフォルダをVSCodeで開く
- `index.adoc`を適宜修正
- VScodeでターミナルを起動する(`` Ctr+Shift+` ``)
- 以下のコマンドを実行
```bash
asciidoctor-pdf -a scripts=cjk -a pdf-theme=./themes/klis-theme.yml -a pdf-fontsdir=./fonts index.adoc 
```
- PDFファイル（`index.pdf`）が生成されたことを確認
- ファイルを修正したら上記コマンドを再実行します

## 基本的な使い方

[上保研究室ナレッジベース](https://joholab.github.io/kb/research/how-to-use-asciidoctor/)を参考にしてください。

## Asciidoctor レファレンス

- https://itcweb.cc.affrc.go.jp/affrit/_media/documents/guide/asciidoc/asciidoc-start.pdf
- https://takumon.github.io/asciidoc-syntax-quick-reference-japanese-translation/
- https://github.com/asciidoctor/asciidoctor/blob/master/README-jp.adoc
