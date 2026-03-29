# 薬局向けLINE受付・自動印刷LP（静的サイト）

個人薬局〜数店舗規模の薬局経営者向けに、
「LINEで受付」「低価格で導入しやすい」「Googleクラウド基盤で管理」を軸として作成した1ページ完結のLPです。

## ファイル構成

- `index.html` : LP本体（セクション構成・文言・CTA・図解）
- `404.html` : Firebase Hosting の404ページ
- `firebase.json` / `.firebaserc` : Firebase設定

## ローカルでの確認方法

### 方法1: Pythonの簡易サーバー

```bash
python3 -m http.server 8080
```

ブラウザで以下にアクセスします。

- <http://localhost:8080>

### 方法2: VS Code の Live Server など

`index.html` をルートとして開いて表示してください。

## Firebase Hosting へのデプロイ方法

事前に Firebase CLI のインストールとログインを実施してください。

```bash
npm install -g firebase-tools
firebase login
```

このリポジトリ直下で実行します。

```bash
firebase deploy --only hosting
```

> すでに `.firebaserc` と `firebase.json` があるため、同一プロジェクトであればそのままデプロイ可能です。

## 文言変更を行う場所

主な文言は `index.html` を編集してください。

- ファーストビュー（キャッチ・サブコピー）
- 課題提起
- 解決策
- 特徴カード
- 図解セクション
- 安心感セクション
- CTA文言

配色や余白などのスタイルは `index.html` 内の `<style>` セクションを調整してください。

## 問い合わせボタンリンクの変更箇所

現在は仮リンクとして `href="#"` を設定しています。
`index.html` 内の以下のCTAリンクを、実運用のURLへ変更してください。

- ヘッダー右上「お問い合わせ」
- ファーストビューの「まずはお問い合わせ」「仕組みを見る」
- ページ下部CTAの各ボタン

例:

```html
<a class="btn btn-primary" href="https://example.com/contact">まずはお問い合わせ</a>
```

## 備考

- 外部ライブラリは使用していません。
- 人物写真は使わず、HTML/CSSベースの図解で構成しています。
- 医療・薬局向けに違和感の少ない、落ち着いた配色とレイアウトを意識しています。
