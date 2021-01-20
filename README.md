# アーム角度を自動検出して動画に追加する。(Tkinterで使いやすい画像処理ツールを作る。）
https://github.com/sassa4771/Find_Angle_Tkinter/tree/main/main<br>
ここのファイルの中身説明↑

## このGitHubでできること
・角度・位置座標を自動検出したいアーム動画を処理して動画にする。
<br><br>
<img src="https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/Gif/ex14.gif" alt="自動トラッキング完成動画イメージ" title="eye03"><br><br>
・Tkinterでできることがわかる（ファイル読み出し、動画トリミング、マウス追従、スライダー作成などなど）
<br><br>
<img src="https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/Gif/ex15.gif" alt="Tkinterできることイメージ" title="eye03"><br><br>

このFind Angleツールを作るまでに学んだ機能などをレッスンとして<br>
lesson1~26までまとめてあるので参考にしてみてください。<br>
https://github.com/sassa4771/Find_Angle_Tkinter/tree/main/tk_lesson<br>
<参考サイト：https://www.youtube.com/watch?v=sAu7uxW85_Y&list=PL1FgJUcJJ03sm4WuVCPMbT0RIf2uMmoAj&index=17>

## 目次
①Tkinterとは？<br>
②必要なライブラリ・動作環境<br>
③ツールの使い方とTkinterの機能紹介<br>
④Tkinter学び方(参考スクリプト付き)<br>
⑤本ツールの作り方（簡易版）<br>

## ①Tkinterとは？
【Tkinterとは】
Tkinterとは、「ティーキンター」や「ティーケーインター」と呼ばれ、Window,Mac,Linuxといった<br>
主要なOSにも対応しているクロスプラットフォームなGUIライブラリです。<br>
(参考：https://www.acrovision.jp/service/data/?p=616)<br><br>

要するに<h3>GUIが作れる！</h3><br>

## ②必要なライブラリ・動作環境
【動作環境：(Let's Note)】<br>
OS:windows10 Pro<br>
CPU:Corei7<br>
メモリ:12GB<br>

【必要なライブラリ】<br>
・dlib
・opencv
・numpy
・PIL(Pillow)

## ③ツールの使い方とTkinterの機能紹介
【ファイルを開く】<br>
まずは、ファイルを開きましょう。<br><br>

このTkinter機能は、こちらのスクリプトを参考にしてください。<br>
[ラベル] https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/tk_lesson/tk_lesson2(Labels).py<br>
[ファイル参照] https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/tk_lesson/tk_lesson23(Browsing%20A%20File).py<br><br>

<img src="https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/Gif/ex1.gif" alt="ファイルを開く" title="Tkinterでファイルを開く"><br><br>
<br>

【選択した動画の閲覧】<br>
no filterを選択して「Show Selected Video」を押すと表示することができる。<br><br>

このTkinter機能は、こちらのスクリプトを参考にしてください。<br>
[ラベル] https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/tk_lesson/tk_lesson2(Labels).py<br>
[ラジオボタン] https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/tk_lesson/tk_lesson8(Radio%20Button).py<br>
[ボタンと機能呼び出し] https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/tk_lesson/tk_lesson4(Button%20And%20Button%20Commands).py<br><br>

<img src="https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/Gif/ex2.gif" alt="選択した動画の閲覧" title="Tkinterでラジオボタン・フィルター処理呼び出し"><br><br>
<br>


【動画の縮小をする】<br>
ただこのままだと、元の動画が大きすぎるのでリサイズをします。<br>
スライダーを利用して、縮小割合を決定します。<br><br>

このTkinter機能は、こちらのスクリプトを参考にしてください。<br>
[ラベル] https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/tk_lesson/tk_lesson2(Labels).py<br>

<img src="https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/Gif/ex3.gif" alt="動画の縮小をする" title="Tkinterで画像の縮小機能呼び出し"><br><br>
<br>


【フィルター処理した動画の閲覧】
ラジオボタンで・フィルターなし・グレースケール・二値化の処理を選択して表示することができます。<br><br>
※二値化処理したものを輪郭抽出で自動追従しているため、背景が黒で、目標点が白でないといけない。<br>
フィルターに関して詳しくは、eyetrackのところで説明しています。<br>
Webカメラでeye tracking（アイトラッキング・視線計測）をする【Windows10】:https://github.com/sassa4771/eyetrack<br><br>

このTkinter機能は、こちらのスクリプトを参考にしてください。<br>
[ラベル] https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/tk_lesson/tk_lesson2(Labels).py<br>
[ボタンと機能呼び出し] https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/tk_lesson/tk_lesson4(Button%20And%20Button%20Commands).py<br><br>

<img src="https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/Gif/ex4.gif" alt="フィルター処理した動画の閲覧" title="Tkinterでラジオボタン・メソッド呼び出し"><br><br>
<br>


【動画の範囲トリミングする】
自動トラッキングしたい点（白色のみトラッキング可能。背景は黒色がベスト）が移動する範囲をトリミングしましょう。

このTkinter機能は、こちらのスクリプトを参考にしてください。<br>
[ラベル] https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/tk_lesson/tk_lesson2(Labels).py<br>
[画像トリミング] https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/tk_lesson/tk_lesson25(Image_Triming).py<br>

<img src="https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/Gif/ex5.gif" alt="画像をトリミングする" title="Tkinterで動画の範囲トリミング"><br><br>
<br>

【トリミングした動画を表示する】
「Check Cut Range」を押して、トリミングした範囲で動画を表示します。<br>
※この処理は、目標点の追従する際に範囲を絞ってノイズが入るのを防ぐために行います。<br><br>

このTkinter機能は、こちらのスクリプトを参考にしてください。<br>
[ラベル] https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/tk_lesson/tk_lesson2(Labels).py<br>
[ボタンと機能呼び出し] https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/tk_lesson/tk_lesson4(Button%20And%20Button%20Commands).py<br><br>

<img src="https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/Gif/ex6.gif" alt="トリミングした動画を表示する" title="Tkinterでトリミング動画の表示"><br><br>
<br>

【】
「Check Cut Range」を押して、トリミングした範囲で動画を表示します。<br>
※この処理は、目標点の追従する際に範囲を絞ってノイズが入るのを防ぐために行います。<br><br>

<img src="https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/Gif/ex6.gif" alt="トリミングした動画を表示する" title="Tkinterでトリミング動画の表示"><br><br>
<br>


【】
「Check Cut Range」を押して、トリミングした範囲で動画を表示します。<br>
※この処理は、目標点の追従する際に範囲を絞ってノイズが入るのを防ぐために行います。<br><br>

<img src="https://github.com/sassa4771/Find_Angle_Tkinter/blob/main/Gif/ex6.gif" alt="トリミングした動画を表示する" title="Tkinterでトリミング動画の表示"><br><br>
<br>

## ④

## ⑤

## ⑦
