## 実行環境

- Docker (1.13.0にて動作確認)

### Dockerコンテナの構成

- OS: ubuntu:16.10
- 言語: Python3.5.2

- Anaconda3-4.1.1
- Chainer1.20
- Keras1.1
- PyDotPlus2.0
- scikit-learn0.18
- Seaborn0.7
- TensorFlow0.12

### インストール

Mac

- [macOS Yosemite 10.10.3以降](https://www.docker.com/products/docker#/mac)
- [上記以外](https://www.docker.com/products/docker-toolbox)(docker-toolbox)

Windows

- [Windows 10 Professional/Enterprise 64-bit](https://www.docker.com/products/docker#/windows)
- [上記以外](https://www.docker.com/products/docker-toolbox)(docker-toolbox)

Windownsでdocker-toolboxを使用する場合、BIOSからvirtualizationをenableにしなければいけないこともある

## 実行方法

Dockerfileのあるディレクトリに移動

```
$ cd machine-learning/machine-learning-study
```

Dockerコンテナ作成(30分程度かかることあり)

Windowsの場合は必要に応じて、docker -> docker.exeに読み替え

```
$ docker build -t scenesk/mls:0.1 .
```

doocker-toolboxを使っている場合は、接続用のIPを確認

```
$ docker-machine ip
```

Dockerコンテナ起動

```
$ docker run -p 8888:8888 -v $(pwd)/jupyter:/root/jupyter -it scenesk/mls:0.1
```

しばらくして起動したら、ブラウザからlocalhost:8888にアクセス

docker-toolboxを使用している場合は、前のステップで確認しておいたIPに置き換え
