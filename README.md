# Lab4SLC espnet ASR チュートリアル

##### 作業ディレクトリに移動 (/path/to/dir は好きなところで良い、相対パスでもOK)
```
cd /path/to/dir
```
##### 本チュートリアル用のディレクトリを作成して移動
```
git clone https://github.com/nara-wu-slc/espnet_asr_tutorial.git
cd espnet_asr_tutorial
```

##### 本チュートリアル用のPython仮想環境を /path/to/dir/espnet_asr_tutorial/.venv に作成
```
python3 -m venv .venv
```

##### 仮想環境を有効化
```
source .venv/bin/activate
```

##### モデル保存用のキャッシュディレクトリの設定を読み込む
##### これをしないと自分のホームディレクトリ下にバカデカいファイルを読み込んでしまって無駄が多い
```
source /slc/share/dot.zshrc.slc
```


##### Pytorchをインストール
```
pip3 install torch torchaudio --index-url https://download.pytorch.org/whl/cu124
```


##### その他必要なライブラリをインストール
```
pip3 install wheel
pip3 install jupyter ipykernel
pip3 install librosa
```

##### espnetをGitHubから取得してインストール
```
git clone https://github.com/espnet/espnet.git
cd espnet
pip3 install --editable ./
cd ..
pip3 install espnet_model_zoo
```

##### Jupyterでの実行前に必要なモデルをダウンロードしておく
```
python3 ./download_models.py
```

##### Jupyterで使うPython環境が仮想環境化になっているかどうか確認する
```
jupyter kernelspec list
```
結果は以下のようになるはず（`/path/to/dir` は作業ディレクトリの名前に読み替えて確認すること）
```
Available kernels:
  python3    /path/to/dir/espnet/espnet_asr_tutorial/.venv/share/jupyter/kernels/python3
```

##### カレントディレクトリで Jupyter Notebook を立ち上げる
```
jupyter notebook ./
```

##### ブラウザで Jupyter Notebook に接続し、asr_test.ipynb を開く

##### Jupyter Notebook上で実行
- Cell > Run all で実行


#### おまけ：インストールを一発で全部実行するためのコマンド群
※作業ディレクトリへの移動後に実行すること
```
git clone https://github.com/nara-wu-slc/espnet_asr_tutorial.git
cd espnet_asr_tutorial
python3 -m venv .venv
source .venv/bin/activate
source /slc/share/dot.zshrc.slc
pip3 install torch torchaudio --index-url https://download.pytorch.org/whl/cu124
pip3 install wheel
pip3 install jupyter ipykernel
pip3 install librosa
git clone https://github.com/espnet/espnet.git
cd espnet
pip3 install --editable ./
cd .. 
pip3 install espnet_model_zoo
python3 ./download_models.py
```
