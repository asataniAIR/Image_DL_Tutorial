# Image_DL_Tutorial
画像に対するDeep Learningの応用チュートリアル。研究開発やアプリケーション開発などに活用してください。
# 開発環境構築
本チュートリアルは[Tensorflow](https://www.tensorflow.org/)をBackendとした[Keras](https://keras.io/ja/)を用います。
OpenCVやmatplotlibなど開発に便利なライブラリも同時にインストールする予定です。各OSに合わせて、開発環境構築を行ってください。
## Windows(CPUのみ使用の場合）
* Anacondaを用いて、開発環境を作成します。以下のURLからWindows向けPython３の最新パッケージをインストールしてください。

https://www.continuum.io/downloads

* WindowsのPowershell、もしくはコマンドプロンプトから以下のコードを実行してください。（本チュートリアルではAIR-Tutorialという名前の環境を作成します）

```
conda create -n AIR-Tutorial python=3.5
```

開発環境が作成できたかを確認するためには以下のコードを実行し、”AIR-Tutorial”の存在をチェックしてみてください。

```
conda info -e
```

作成した環境を起動しましょう！以下のコードを実行してください。

```
activate AIR-Tutorial
```

左側に（AIR-Tutorial）と出てくれば、環境を起動できています。この環境にライブラリをインストールしていきましょう。以下のコードを入力してください。

```
pip install tensorflow
conda install -c https://conda.anaconda.org/menpo opencv3
conda install scipy
conda install h5py
pip install matplotlib
pip install keras 
```

上記コードで、tensorflow,opencv,scipy,h5py,matplotlib,kerasがインストールできました。チュートリアルを開始しましょう！


## Windows(GPUも活用する場合:NVIDIAのGPUを想定しています）

* Anacondaを用いて、開発環境を作成します。以下のURLからWindows向けPython３の最新パッケージをインストールしてください。

https://www.continuum.io/downloads

* WindowsのPowershell、もしくはコマンドプロンプトから以下のコードを実行してください。（本チュートリアルではAIR-Tutorial-gpuという名前の環境を作成します）

```
conda create -n AIR-Tutorial-gpu python=3.5
```

GPUを活用するために、CUDA Toolkitをインストールします。以下のURLからWindows向けのツールキットをインストールしてください。

https://developer.nvidia.com/cuda-downloads

Deep Learningを高速化するためのライブラリであるcuDNN5.1もダウンロードします。以下のURLからダウンロードしてください。cuDNNはダウンロードに登録（無料）が必要ですので、忘れず！

https://developer.nvidia.com/cudnn 


ダウンロードしたファイルには、cudnn64_5.dll,cudnn.h,cudnn.libが入っていますので、所定の位置に移動させます。

* cudnn64_5.dll →　C:\ProgramFiles\NVIDIA GPU Computing Toolkit\CUDA\v8.0\bin
* cudnn.h　→　C:\ProgramFiles\NVIDIA GPU Computing Toolkit\CUDA\v8.0\include
* cudnn.lib　→　C:\ProgramFiles\NVIDIA GPU Computing Toolkit\CUDA\v8.0\lib\x64

これでGPUを活用する準備ができました。作成した環境を起動しましょう！以下のコードを実行してください。

```
activate AIR-Tutorial
```

左側に（AIR-Tutorial-gpu）と出てくれば、環境を起動できています。この環境にライブラリをインストールしていきましょう。以下のコードを入力してください。

```
pip install tensorflow-gpu
conda install -c https://conda.anaconda.org/menpo opencv3
conda install scipy
conda install h5py
pip install matplotlib
pip install keras 
```
以上でインストールは完了です。GPUが動いているかを確認するために、以下のコードを入力して起動時にGPUを立ち上げているかを確認しましょう。

```
python　　#pythonを起動してください
>>>import keras 　　　　#kerasをimportします
```

以下が表示されればGPUを起動できています。

```
Using TensorFlow backend.
I c:\tf_jenkins\home\workspace\release-win\device\gpu\os\windows\tensorflow\stream_executor\dso_loader.cc:135] successfully opened CUDA library cublas64_80.dll locally
I c:\tf_jenkins\home\workspace\release-win\device\gpu\os\windows\tensorflow\stream_executor\dso_loader.cc:135] successfully opened CUDA library cudnn64_5.dll locally
I c:\tf_jenkins\home\workspace\release-win\device\gpu\os\windows\tensorflow\stream_executor\dso_loader.cc:135] successfully opened CUDA library cufft64_80.dll locally
I c:\tf_jenkins\home\workspace\release-win\device\gpu\os\windows\tensorflow\stream_executor\dso_loader.cc:135] successfully opened CUDA library nvcuda.dll locally
I c:\tf_jenkins\home\workspace\release-win\device\gpu\os\windows\tensorflow\stream_executor\dso_loader.cc:135] successfully opened CUDA library curand64_80.dll locally
>>>
```
それでは、チュートリアルを開始しましょう！


## Mac・・・作成中
## Ubuntu・・・作成中
