# WebNFC_VCF

Web NFC APIを活用して、NFCタグとvCard（`.vcf`：電子名刺）形式の連絡先データの読み書きを行うためのシンプルなWebアプリケーションです。

## 📝 概要 (Overview)

このリポジトリは `index.html` のみで構成された軽量なフロントエンドアプリです。
Androidスマートフォンのブラウザ（Chromeなど）から直接NFCタグにタッチすることで、名刺代わりとなる連絡先データ（vCard）をNFCタグに書き込んだり、読み込んだりすることが可能です。

## ✨ 主な機能 (Features)

- **vCardデータの読み取り**: NDEFフォーマットで記録されたNFCタグからvCardデータ（連絡先情報）を読み込みます。
- **vCardデータの書き込み**: Webブラウザ上からNFCタグに対して、vCardデータ（`text/vcard` など）を書き込みます。
- **フロントエンド完結**: サーバーサイドの処理やビルド環境を必要とせず、ブラウザだけで動作します。

## 📱 動作環境 (Requirements)

Web NFC APIは、セキュリティ上の理由から **HTTPS環境**（またはローカルの `localhost`）でのみ動作します。

- **対応OS**: Android
- **対応ブラウザ**: Google Chrome for Android（バージョン89以降）などのChromium系ブラウザ
- **デバイス要件**:
  - 端末のNFC機能が有効になっていること
  - NDEF（NFC Data Exchange Format）対応のNFCタグ（NTAG213, NTAG215, NTAG216 など）

*(※ 2026年3月現在、iOSのSafariはWeb NFC APIをサポートしていないため動作しません)*

## 🚀 使い方 (Usage)

### 1. ローカルでの動作確認

ローカル環境でテストする場合、`file://` プロトコルではなくローカルサーバーを立ち上げる必要があります。

```bash
git clone [https://github.com/kmtshn/WebNFC_VCF.git](https://github.com/kmtshn/WebNFC_VCF.git)
cd WebNFC_VCF

# 例: Python3のローカルサーバー機能を使う場合
python -m http.server 8000
