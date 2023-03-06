---
sidebar_position: 1
---

# 使い方説明

## 1. Poke-Controller Modifiedの導入

### 1-1. Poke-Controller Modified インストールスクリプトのダウンロード

以下のツイートのリンクをブラウザで開き、zipファイルをダウンロードして [展開](https://support.microsoft.com/ja-jp/windows/8d28fa72-f2f9-712f-67df-f80cf89fd4e5#ID0ED-button) します。<br />
https://twitter.com/Rokkoku_I/status/1505534135670288385 [^1]

[^1]: 本スクリプトは、「[ろっこく](https://twitter.com/Rokkoku_I/)」さんが作成された、「Python環境構築からPokeControllerの導入、実行を代行してくれるbatファイル(v05)」です。

### 1-2. Poke-Controller Modified インストールスクリプトの実行

展開したフォルダ内の、BatsForPokecon_v05 > PokeController 内の3つのバッチファイル

- 1_PokeConEnv.bat
- 2-2_ClonePokeConModified.bat
- 3-2_ExecutePokeConModified.bat

を上から順に実行します。（うまく行かない場合は、管理者権限で実行してみてください）

なお、[1つ目](## "1_PokeConEnv.bat")は5〜30分程度（PCや回線のの速度によって異なります）時間がかかります。
「Poke-Controller-Modifiedの環境構築が完了しました」と表示されるまで、辛抱強くお待ち下さい。<br />

[2つ目](## "2-2_ClonePokeConModified.bat")は、1分程度で完了します。<br />

[3つ目](## "3-2_ExecutePokeConModified.bat")で、Poke Controller Modifiedが起動します。

## 2. 機器の接続

以下を順に接続します。

1. 「USB-シリアル変換モジュール[^2]」と「Arduino Leonardo[^3]」を、ジャンパケーブル [^4] 2本で接続します。<br />
GND-GND, TXD-RX←0 を接続し、以下の写真のようにしてください。

[^2]:小さいほうの基板
[^3]:大きいほうの基板
[^4]: ジャンパケーブルは、1本ずつちぎってご利用ください。予備をたくさん入れていますが、必要なのは2本だけです。

![example of jumper cable connections](/img/jumper-cable-connection.webp)

2. 「USB-シリアル変換モジュール」とPCを、Type-Cケーブルで接続します。
3. 「Arduino Leonardo」と「ニンテンドーSwitchに接続したDock」を、Micro USBケーブルで接続します。
4. キャプチャボードをPCのUSBポートに接続します。<br />
5. キャプチャボードと「ニンテンドーSwitchに接続したDock」を、HDMIケーブル[^5]で接続します。

[^5]:HDMIケーブルとは、Switchとテレビ等を接続するケーブルです。<br />
テレビ等から抜いて、テレビ等に刺さっていた側の端子をキャプチャボードに刺してください。

ここまで完了すると、以下の図のような配線となります。

![example of all connections](/img/all-connections.webp)

## 3. 利用したい自動化プログラムの追加

PokeController ModifiedのPythonCommandsフォルダや、その2つ上の階層のTemplatesフォルダにファイルを配置します。<br />
（PythonCommandsフォルダは、PokeController Modifiedを起動して、画面右下のコマンド選択欄のフォルダアイコンをクリックすると開けます）

詳しくは、利用したい自動化プログラムに付属の説明をご覧ください。

自動化プログラムは、インターネット上で公開されているもの利用するか、ご自身で作成していただく必要があります。<br />
[こちらのページ](/docs/programs/) に、各種のおすすめプログラムを掲載しております。

## 4. Poke-Controller Modifiedの起動と実行

1. 既にPoke Controller Modifiedが開いている場合は、一旦閉じます。
2. 3-2_ExecutePokeConModified.bat を実行し、Poke Controller Modifiedを起動します。
3. 画面上部の映像キャプチャデバイスの選択欄から、「USB Video」を選択します。
4. 「デバイスマネージャー」を開き、「ポート（COMとLPT）」から「USB-SERIAL CH340」と書いてあるものを探してポート番号を見つけます。<br />
   例えば、「USB-SERIAL CH340（COM5）」と書いてある場合、ポート番号は「5」です。<br />
   そして、見つけたポート番号を、PokeController Modifiedの画面左下のポート設定欄に設定します。[^6]
5. 画面右下のコマンド選択欄から使用したいコマンドを選択し、Startボタンをクリックします。

[^6]:見つからない場合は、デバイスマネージャーで右クリックし、「ハードウェア変更のスキャン」をクリックしてください。

これで、自動化プログラムが実行されます。<br />
なお、自動操作時には他の有線・無線のコントローラは接続を解除してご利用ください。
