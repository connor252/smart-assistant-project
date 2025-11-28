本サービス  
smart-assistant-projectは、  
「詠唱(起動ワード)→ キャラ召喚 → コマンド」  
という異世界っぽい世界観で、電気や家電などのIoTデバイスを音声操作するスマートホームシステムです。  
例)定義する、スライム召喚 → スライム、電気をつけて

---

## プロジェクト概要
- PCやRaspberry Piをハブにして、部屋のライト・デバイスを制御
- 「キャラ召喚」型の音声インターフェース
- 将来的には3Dアバター(Unity)やスマホアプリからの操作も対応予定
※ 現在は 設計・プロトタイプレベル(WIP) です。

---

## ディレクトリ構成(予定)

```
smart-assistant-project/
├── README.md
├── LICENSE
├── docs/
│   ├── command-spec.md      # コマンド仕様書
│   └── architecture.md      # アーキテクチャ図・設計メモ（予定）
├── config/
│   ├── core.yaml            # システム共通設定
│   └── user.yaml            # ユーザーごとの設定（詠唱ワードなど）
├── pc-controller/
│   ├── main.py              # ローカルPC側エントリポイント
│   ├── command_parser.py    # 詠唱・キャラ名・コマンドの解析
│   └── action_handler.py    # 解析結果に応じた処理分岐
├── character/
│   ├── base_character.py    # キャラ共通の抽象クラス
│   ├── dullahan.py          # デュラハンの挙動定義
│   └── manager.py           # キャラの登録・切り替え管理
├── device/
│   ├── light/
│   │   ├── base.py          # ライト共通IF
│   │   └── pc_light_driver.py   # PC 上のライト制御（お試し用）
│   └── ambience/
│       ├── base.py          # 環境演出（BGM / エフェクト）共通IF
│       └── pc_ambience_driver.py
├── avatar-unity/            # 3D アバター（Unity）関連プロジェクト
├── aws-backend/             # AWS Lambda / API Gateway / IoT Core など
├── iot/                     # Raspberry Pi / センサー / 実機制御コード
└── mobile-ui/               # スマホアプリ（Flutter / React Native 想定）
```

---

## 目標バージョンイメージ

- **v1**: 
  - PC上で音声コマンド → ライト(または疑似ライト)のON/OFF
  - 詠唱 + キャラ名 + コマンドの一連のフローが動く状態

- **v2**: 
  - Raspberry PiやLEDテープなどの実機IoTデバイス連携
  - AWS(IoT Core/Lambda/API Gateway)経由で制御

- **v3**: 
  - 3Dキャラ(Unity)表示
  - キャラごとに演出や応答が変わる
  - スマホアプリからの操作・ウィジェット連携

---

## 仕様技術(予定を含む)

**言語**
- Python
- TypeScript
- C#

**フレームワーク / ライブラリ**
- React / React Native
- Unity

**クラウド / インフラストラクチャ**
- AWS IoT Core
- AWS Lambda
- Amazon API Gateway
- AWS CDK

---

## ライセンス

このリポジトリのコード・設定ファイル・ドキュメントは、原則として

**Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)**

で公開しています。

商用利用は禁止です。詳細は `LICENSE` を確認してください。

























---


##  目的

- ライト・センサー・ホログラムなど **複数のIoTデバイスをクラウド経由で制御**
- 音声コマンド＋人感センサーで動く “スマートルーム” を構築

##  使用技術

**IoT / ハードウェア**  
- Raspberry Pi  
- LED  
- 人感センサー（PIR）  
- マイク入力（音声認識）

**クラウド（AWS）**  
- AWS IoT Core  
- AWS Lambda  
- API Gateway  
- DynamoDB（予定）

**ソフトウェア**  
- Python / Unity  
- Linux  
- Flutter or React Native

## License
This project is licensed under the CC BY-NC 4.0 License.
Commercial use is prohibited.
