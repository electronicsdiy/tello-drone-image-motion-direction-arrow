# Display Tello Drone's 1st Person Camera Frame Image, Detected Objects' Motion Vector, and Drone's Status Information

<img width="958" alt="スクリーンショット 2021-08-12 0 41 06" src="https://user-images.githubusercontent.com/87643752/129060904-81aec5e8-6b9d-4963-9238-61aa7ce655fa.png">

次の画像では、Telloの正面にあるTV画面の上端に沿って、「↓」がたくさん並んでいる。
これは、ホバリング中のTelloの機体がわずかに上下に揺れていた中で、このシーンを「p」ボタンで撮影した瞬間、**Telloが上方向に揺れていたため、Telloから見てTV画面が（相対的に）下方向に動いて見えたから**だと考えらえる。

<img width="849" alt="スクリーンショット 2021-08-11 23 50 19" src="https://user-images.githubusercontent.com/87643752/129139812-f57b97de-09a1-49bb-88a6-d091eb95eaab.png">


## 解説記事

#### [ドローンのカメラ画像にモーション解析をリアルタイム実行！画面内の物体の移動方向を矢印表示♫](https://qiita.com/electronics_diy721/items/40745cd41baf11fc1d7d)

## **使い方** 

1. このリポジトリの資源をgit cloneしたノートPCを、TelloにWifi接速する。
2. **examplesディレクトリ**に移動して、Python3系で、**python3 motion_arrow_flight_info.py**を実行する。

> % python3 motion_arrow_flight_info.py


## 1. Telloドローンのキーボード操作

TelloとWifi回線でつながっているノートPCのキーボードから、Telloを操作します。

* i : 離陸
* w: 前進
* s : 後進
* a : 左移動
* d : 右移動
* e : 時計回り30度回転
* q : 反時計回り30度回転
* r :  上昇
* f :  降下
* g : 着地
* p : フレーム画像のファイル保存（※）

※ 画像ファイルは、カレントディレクトリ（exampleディレクトリ直下）に出力されます。

※ ファイル名は、**frame_img_shot_XXXX年XX月XX日XX/XX/XX.jpg**です。最後はhour, minutes, ミリ秒です。

## 2. Telloカメラ画像のウィドウ表示（左右２画面）

離陸前から、ノートPCにWindowが１つ立ち上がり、特徴点を検出した人物や動物、物体の運動ベクトル（方角＋速度）の推定結果を、矢印で表示します。（青矢印）
青矢印は、対象となる物体の内部や外周の複数の座標位置に表示されます。各矢印は、それぞれの位置における対象物体（人間、動物を含む）の運動ベクトルを示しています。

また、画面全体の移動の運動ベクトルを、赤矢印（１つだけ）表示します。

さらに画面の左上に、Telloドローンの現在高度が表示されます。

画面の左側に表示されるTelloカメラ画像の受信と、PCのキーボード入力によるTelloの操縦は、**DJITelloPyライブラリ**を使います。

- https://github.com/damiafuentes/DJITelloPy

## __事前準備__

### このリポジトリの資源の取得

このリポジトリ内の資源を、ここにある通りのディレクトリ構成でダウンロードしてください。
（git clone又は手動zipダウンロード）

