# Image_DL_Tutorial
画像に対するDeep Learningの応用チュートリアル。研究開発やアプリケーション開発などに活用してください。
# 開発環境構築(3月20日作成)
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


## Mac
- Homebrewがインストール済みか確認しましょう。

```
brew --version  
```
Homebrew 1.1.10などと表示されたらインストール済みです。

- インストールされていなかった場合は、以下のコマンドでインストールできます。

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

- Homebrew環境をアップデートしてpyenvをインストールしましょう。

```
brew update && brew upgrade
brew install pyenv
```

- pyenvの設定を.bash_profileに追記して反映させます。

```
echo 'export PYENV_ROOT="${HOME}/.pyenv"' >> ~/.bash_profile
echo 'export PATH="${PYENV_ROOT}/bin:$PATH"' >> ~/.bash_profile
echo 'eval "$(pyenv init -)"' >> ~/.bash_profile
source ~/.bash_profile
```

- Anacondaをインストールします。

```
pyenv install anaconda3-4.2.0
pyenv global anaconda3-4.2.0
```

以下のコマンドで`Python 3.5.3 :: Continuum Analytics, Inc.`と表示されれば正しくインストールできています。

```
python --version
```

- 開発環境を作りましょう！

AIR-Tutorialという名前の環境を作成します。

```
conda create -n AIR-Tutorial python=3.5
```

以下のコマンドでAIR-Tutorial環境が作成できたことが確認できます。

```
conda info -e
```

- 作成した開発環境を起動しましょう。

```
echo 'alias activate="source $PYENV_ROOT/versions/anaconda3-4.2.0/bin/activate"' >> ~/.bashrc
source ~/.bashrc
activate AIR-Tutorial
```
左側に（AIR-Tutorial）と出てくれば、環境を起動できています。この環境にライブラリをインストールしていきましょう。

- Tensorflowをインストールします。

CPUのみの場合：

```
pip install --ignore-installed --upgrade https://storage.googleapis.com/tensorflow/mac/cpu/tensorflow-1.0.1-py3-none-any.whl
```

GPUありの場合：

```
pip install --ignore-installed --upgrade https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl
```

- その他必要なライブラリをインストールしましょう。

```
conda install -c https://conda.anaconda.org/menpo opencv3
conda install scipy
conda install h5py
pip install matplotlib
pip install keras 
```

お疲れ様です！
それではチュートリアルを始めましょう！


## Ubuntu・・・作成中
