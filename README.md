# Lab4SLC espnet TTS チュートリアル

```
# 作業ディレクトリに移動 (/path/to/dir は好きなところで良い、相対パスでもOK)
cd /path/to/dir

# 本チュートリアル用のディレクトリを作成して移動
git clone https://github.com/nara-wu-slc/espnet_tts_tutorial.git
cd espnet_tts_tutorial

# 本チュートリアル用のPython仮想環境を /path/to/dir/espnet_tts_tutorial/.venv に作成
python3 -m venv .venv

# 仮想環境を有効化
source .venv/bin/activate

# モデル保存用のキャッシュディレクトリの設定を読み込む
# これをしないと自分のホームディレクトリ下にバカデカいファイルを読み込んでしまって無駄が多い
source /slc/share/dot.zshrc.slc
```

```
# Pytorchをインストール
pip3 install torch torchaudio --index-url https://download.pytorch.org/whl/cu124
```

```
# その他必要なライブラリをインストール
pip3 install wheel
pip3 install jupyter ipykernel
```

```
# espnetをGitHubから取得してインストール
git clone https://github.com/espnet/espnet.git
cd espnet
pip3 install --editable ./
cd ..
pip3 install espnet_model_zoo
```

```
# 今使っている仮想環境をJupyter Notebookで使えるようにする
ipython3 kernel install --user --name=.venv
```

```
# カレントディレクトリで Jupyter Notebook を立ち上げる
jupyter notebook ./
```

```
# ブラウザで Jupyter Notebook に接続し、tts_test.ipynb を開く（下の画像参照）
```
<img width="345" alt="jupyter launch" src="https://github.com/user-attachments/assets/6ea666dd-6480-4dfe-97cf-a2a6481c35ed">

```
# 右上の Logout の下あたりにある、現在使っているカーネルが .venv になっているか確認する（下の画像参照）
```
<img width="258" alt="jupyter kernel" src="https://github.com/user-attachments/assets/bc9c5c1a-ac57-408b-8c08-c663a896b61c">

```
# もし違っていたら、Kernel > Change Kernel から .venv を選ぶ（下の画像参照）
```
<img width="719" alt="change kernel" src="https://github.com/user-attachments/assets/294c5036-b0ae-4dd1-aa73-314d2c8b9a0f">

```
# 
```
