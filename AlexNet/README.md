# AlexNet Tutorial

AlexNetは一般画像認識のコンペティションであるILSVRCにおいて、2012年に優勝したDeep Learningモデルです。
Deep Learningブームの火付け役といってもよい、記念碑的なネットワークですので、是非活用してください。

## AlexNet概要

AlexNetは多クラス分類を行う畳みこみニューラルネットワークです。畳みこみ層とプーリング層を重ね、全結合層、ソフトマックス層へとつなげる、多クラス分類を可能とする基本骨格を示した重要なモデルです。


##　チュートリアル

ファイル構成
* AlexNet.py
    AlexNetのモデル構造が記述されています。

* AlexNet_Train.py
    AlexNetを学習させます。

* AlexNet_Demo.py
    学習済みモデルを読み込み、実際に画像を認識させます。

### データベースを作成する
今回は[Caltech101](http://www.vision.caltech.edu/Image_Datasets/Caltech101/#Download)データセットの学習をデモとして用います。
上記Caltech101データセットから 101_ObjectCategories.tar.gz (131Mbytes)をダウンロードしてください。
今後は様々なデータセットをダウンロードする予定ですので、”Dataset”フォルダを別のフォルダに作成して、その中にデータを解凍していただいたほうが良いでしょう。

### AlexNetのモデル構造を記述する（AlexNet.py）
AlexNetの構造を、Kerasを用いて記述していきましょう。
もともとのAlexNetは1000クラスの分類を行う構造を持っていますが、今回は最終層を101クラスに変更してモデルを記述します。


### 学習させる（AlexNet_Train.py）
Caltech101データセットを学習させましょう。

### FineTuningを行う（AlexNet_Train.py）
学習の収束に時間がかかってしまう。。。。そんな時は、FineTuningの出番です。

### 学習済みモデルを用いて物体を認識する（AlexNet_Demo.py）
学習済みのモデルを読み込んで、新たな画像を認識させてみましょう。

### 学習のテクニック