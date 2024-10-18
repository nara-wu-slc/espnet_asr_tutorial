# Lab4SLC espnet TTS チュートリアル

##### 作業ディレクトリに移動 (/path/to/dir は好きなところで良い、相対パスでもOK)
```
cd /path/to/dir
```
##### 本チュートリアル用のディレクトリを作成して移動
```
git clone https://github.com/nara-wu-slc/espnet_tts_tutorial.git
cd espnet_tts_tutorial
```

##### 本チュートリアル用のPython仮想環境を /path/to/dir/espnet_tts_tutorial/.venv に作成
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
  python3    /path/to/dir/espnet/espnet_tts_tutorial/.venv/share/jupyter/kernels/python3
```

##### カレントディレクトリで Jupyter Notebook を立ち上げる
```
jupyter notebook ./
```

##### ブラウザで Jupyter Notebook に接続し、tts_test.ipynb を開く（下の画像参照）
<img width="345" alt="jupyter launch" src="https://github.com/user-attachments/assets/6ea666dd-6480-4dfe-97cf-a2a6481c35ed">

##### Jupyter Notebook上で実行
- Cell > Run all で実行
<img width="1159" alt="Run all" src="https://github.com/user-attachments/assets/a5a4d106-2fb3-4d61-8126-5c808c250a7a">

- 入力欄が表示されたら適当な英文を入れる
<img width="726" alt="input" src="https://github.com/user-attachments/assets/d858677f-5f84-4ad1-9b0a-afb977322693">

- 合成音声がNotebook上で再生できる（whileでループしているので何度でも試せる）
<img width="387" alt="output" src="https://github.com/user-attachments/assets/28785447-6934-41b1-b0df-4a37ffece62e">


#### おまけ：インストールを一発で全部実行するためのコマンド群
※作業ディレクトリへの移動後に実行すること
```
git clone https://github.com/nara-wu-slc/espnet_tts_tutorial.git
cd espnet_tts_tutorial
python3 -m venv .venv
source .venv/bin/activate
source /slc/share/dot.zshrc.slc
pip3 install torch torchaudio --index-url https://download.pytorch.org/whl/cu124
pip3 install wheel
pip3 install jupyter ipykernel
git clone https://github.com/espnet/espnet.git
cd espnet
pip3 install --editable ./
cd .. 
pip3 install espnet_model_zoo
python3 ./download_models.py
```
