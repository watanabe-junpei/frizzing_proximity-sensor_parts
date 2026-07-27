# Fritzing用回路図・パーツ作成手順

## 回路図の作成のために使用するツール

- Fritzing
  - 無料版を使用するため、FritzingのGitHubからインストールする。
  -下記サイトを参考にインストールしてください。
  - https://zenn.dev/suzuky/articles/3d386719984beb
- Inkscape

## 作成するファイル

- **`.fzpz`**
  - Fritzingで作成したパーツファイル
- **`.svg`**
  - 作成したセンサー画像のSVGファイル
- **`.png`**
  - Inkscapeで作成したセンサー画像の編集用ファイル
- **`.fzz`**
  - Fritzingで作成した回路図のデータ
- **`.png`**
  - Fritzingで作成した回路図をPNGに変換したもの

## 作成例

作成例は下記などにある。

- https://github.com/watanabe-junpei/fritzing-parts
- https://github.com/watanabe-junpei/frizzing_proximity-sensor_parts/tree/main

## 作成手順

手順の一例を記載する。最終的に上記のファイルが作成できていれば問題ない。
「Inkscape Fritzing」などで検索すれば情報は出てくるはず。

### 1. 類似のパーツファイルを検索する

- Fritzingから類似のパーツファイルを検索する。
「`Grove`」と検索して、GND、VCC、SDA、SCLのコネクタが存在するパーツを使用した方がよい。
<img width="1137" height="628" alt="スクリーンショット 2026-07-27 8 27 24" src="https://github.com/user-attachments/assets/0aa583d7-d04c-462c-812c-57ed8df65ee5" />
### 2. SVGファイルをエクスポートする

- 「`Edit (new parts editor)`」から「エクスポート」を行い、SVG形式で画像データをエクスポートする。
<img width="1195" height="660" alt="スクリーンショット 2026-07-27 8 28 15" src="https://github.com/user-attachments/assets/093f1fb3-e61d-47f4-8a3e-d973470ddb2c" />

### 3. センサー画像を作成する

- エクスポートしたSVGをInscapeに取り込む。
<img width="708" height="618" alt="スクリーンショット 2026-07-27 8 33 24" src="https://github.com/user-attachments/assets/6f199674-1226-4d86-9ab2-ea067cffeed3" />

- 取り込んだSVGファイルを編集してセンサーの画像を作成する。
  - GND、VCC、SDA、SCLと記載されたコネクタの部分は流用した方がよい（既にFritzingで使用できる状態で作成されているため）。

  - センサーの穴が空いている部分、黒いIC（コア）がある部分など図形の特徴的な部分だけ再現し、それ以外の細かい抵抗などの部分は省略してよい。

- 作成したセンサー画像をPNGファイルおよびSVGファイルでエクスポートする。
<img width="1440" height="900" alt="スクリーンショット 2026-07-27 9 03 37" src="https://github.com/user-attachments/assets/53ba2050-66f5-4291-bdf9-0e273a1d91c4" />

### 4. Fritzingへ取り込む

- 作成したセンサー画像のSVGファイルをFritzingに取り込む。
  - 「`Edit (new parts editor)`」したパーツから「`File > Load image for view...`」などを実行して取り込む。

<img width="1440" height="900" alt="スクリーンショット 2026-07-27 10 02 23" src="https://github.com/user-attachments/assets/0a76b7c9-bddc-40f2-844b-b9b53664624c" />

<img width="1440" height="900" alt="スクリーンショット 2026-07-27 10 02 34" src="https://github.com/user-attachments/assets/7459bc04-59a0-4c9a-a3c5-eba559f53961" />


- 「`Icon`」タブを選択したあと、「`File > Reuse Breadboard Image`」を選択してパーツファイルのアイコンも変更する。
<img width="1440" height="900" alt="スクリーンショット 2026-07-27 10 05 35" src="https://github.com/user-attachments/assets/d9ba44dd-7db0-4042-893c-0e34a8d98004" />

- 「`Metadata`」タブを選択し、適宜作成したセンサーの情報に書き換える。
<img width="1440" height="900" alt="スクリーンショット 2026-07-27 10 07 02" src="https://github.com/user-attachments/assets/c706ee79-f850-42da-b1ae-26a7a61d12b0" />

- 「`Connector`」タブを選択し、GND、VCC、SDA、SCLが存在しているか確認する。
<img width="1440" height="900" alt="スクリーンショット 2026-07-27 10 07 33" src="https://github.com/user-attachments/assets/d4074d9c-ee8a-4576-82cf-afda5127f5e0" />

- 「`File > Save as New Part`」で保存する。

  - `.fzpz`ファイルをエクスポートする。 
<img width="1440" height="900" alt="スクリーンショット 2026-07-27 10 08 18" src="https://github.com/user-attachments/assets/ff526ada-dbeb-4b13-bcb7-1c7e3d3a1f09" />


### 5. 回路図を作成する

- 回路図を作成する。
  - 既存のブレッドボード画像は削除する。
  - パーツデータから「`raspi`」と検索し、「`Raspberry Pi 3`」の画像をブレッドボード上に配置する。

 
<img width="1440" height="900" alt="スクリーンショット 2026-07-27 10 14 26" src="https://github.com/user-attachments/assets/13412481-c79e-49fb-8b12-d1c18e58df77" />

- 作成したセンサーのパーツファイルをブレッドボード上に配置する。
<img width="1142" height="631" alt="スクリーンショット 2026-07-27 11 04 31" src="https://github.com/user-attachments/assets/a7e30af5-96b4-4dea-974b-71b1d6e46b0d" />

- 配置したラズパイの画像とセンサー画像を、実際に結線した通りに線を繋ぐ（色も合わせる）。
<img width="1440" height="900" alt="スクリーンショット 2026-07-27 10 19 06" src="https://github.com/user-attachments/assets/5aa630e2-09c2-4751-a708-b3893e0fc460" />

- `.fzz`ファイル、`.png`ファイルをエクスポートする。
  - 「名前をつけて保存」をクリックし、'.fzz'ファイルを保存。
<img width="1440" height="900" alt="スクリーンショット 2026-07-27 10 26 20" src="https://github.com/user-attachments/assets/948b6a7c-9b2f-4d1b-af3c-adbe629e70a2" />

  - 「エクスポート」→「as image」→「PNG」で`.png`ファイルを保存。
<img width="1440" height="900" alt="スクリーンショット 2026-07-27 10 27 06" src="https://github.com/user-attachments/assets/ab232ad7-d143-4512-9cdf-df1c411695a0" />

### 6. 成果物を共有する

- 作成した各種ファイルを作業者に共有する。

## 参考記事

- https://qiita.com/saka-guti/items/cec81b7c43d811be65c7#%E4%BD%9C%E6%88%90%E6%89%8B%E9%A0%86
- https://leico.github.io/TechnicalNote/Arduino/fritzing-part
