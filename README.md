
## batファイル
拡張子.bat
単純なWindowsコマンドのまとめ
コマンドの羅列で変数のセットなどはできない


## WSH
Windows Script Hostの略
基本的なファイルの入出力やIEの操作など。
Linuxでいうシェルスクリプト
実際の言語はVBScriptやJScriptなど。
Windows系のためか、文字コードがShift-JIS一択
fileSplit.jse(Excelをドラック＆ドロップして、シートごとに分割)

## power shell
マイクロソフトが開発したCUIのシェル
コマンドプロンプトやWSHの強化版。
.NETを利用できる。ある程度複雑な処理はこれで

https://qiita.com/yokra9/items/d95abda8a795d4e19e0e



## ファイル読み込み
Import-csv
https://bgt-48.blogspot.com/2019/04/powershellcsv.html

通常のファイルポインタを使う方法
```
$file = New-Object System.IO.StreamReader($fileName, [System.Text.Encoding]::GetEncoding("sjis"))
#1行ごとの読み込み
while (($line = $file.ReadLine()) -ne $null)
{
    Write-Host($line)
}
$file.Close()
```
https://qiita.com/sukakako/items/ede96f6227f010a0f328

## powershellの実行
.\genereteSetting.ps1 account01←引数

- generateSetting.ps1 CSVから設定情報を取り込み、テンプレートファイル(template.txt)に置換して、保存する


## 参考URL
https://qiita.com/asterisk9101/items/5d25bef660c88ae9bcea

Linuxコマンドとの比較
|  Linux  |  Windows  |
| ---- | ---- |
|  ls -la  |  Get-ChildItem  |
|  cp 元ファイル コピー先ファイル |  Rename-Item 元ファイル コピー先ファイル |

よく出てくる環境変数
|  環境変数  |  意味  |
| ---- | ---- |
|  $OutputEncoding.EncodingName  |  現在使われているエンコード  |

