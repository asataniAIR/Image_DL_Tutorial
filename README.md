# Image_DL_Tutorial
画像に対するDeep Learningの応用チュートリアル。研究開発やアプリケーション開発などに活用してください。
# 開発環境構築
本チュートリアルは[Tensorflow](https://www.tensorflow.org/)をBackendとした[Keras](https://keras.io/ja/)を用います。
OpenCVやmatplotlibなど開発に便利なライブラリも同時にインストールする予定です。各OSに合わせて、開発環境構築を行ってください。
## Windows(CPUのみ使用の場合）
* Anacondaを用いて、開発環境を作成します。以下のURLからWindows向けPython３の最新パッケージをインストールしてください。

https://www.continuum.io/downloads

* WindowsのPowershell もしくは　コマンドプロンプト　から以下のコードを実行してください。（本チュートリアルではAIR-Tutorialという名前の環境を作成します）

```
conda create -n AIR-Tutorial python=3.5
```

開発環境が作成できたかを確認するためには以下のコードを実行し、”AIR-Tutorial”の存在をチェックしてみてください。

```
conda info -e
```

作成した環境に入りましょう！以下のコードを実行してください

```
activate AIR-Tutorial
```

左側に（AIR-Tutorial）と出てくれば、環境にを起動できています。この環境にライブラリをインストールしていましょう。以下のコードを入力してください。

```
pip install tensorflow
conda install -c https://conda.anaconda.org/menpo opencv3
conda install scipy
conda install h5py
pip install keras 
```

上記コードで、tensorflow,opencv,scipy,h5py,kerasがインストールできました。チュートリアルを開始しましょう！


## Windows(GPUも活用する場合:NVIDIAのGPUを想定しています）・・・作成中
## Mac・・・作成中
## Ubuntu・・・作成中
