# 株式会社coboa Webサイト開発記録

## プロジェクト概要
株式会社coboaのコーポレートサイトとcoboa academy LPの開発

## 作成したファイル

### メインサイト
- `index.html` - コーポレートサイト（トップページ）
- `privacy-policy.html` - プライバシーポリシー
- `terms-of-service.html` - 利用規約

### サブサイト
- `academy/index.html` - coboa academy ランディングページ

### 画像フォルダ
- `images/` - ロゴ画像格納フォルダ
  - `coboa-logo.png` - coboaロゴ
  - `coboa-academy-logo.png` - coboa academyロゴ

## 技術仕様

### 共通要件
- **フレームワーク**: 純粋なHTML/CSS/JavaScript（フレームワーク不使用）
- **デザイン**: モバイルファーストのレスポンシブデザイン
- **メインカラー**: #cc0b0a（赤色）
- **フォント**: Hiragino Kaku Gothic ProN, Hiragino Sans, Meiryo
- **外部ライブラリ**: Font Awesome 6.0.0 CDN

### 機能実装
- スムーススクロール
- ハンバーガーメニュー（モバイル対応）
- スクロールアニメーション（フェードイン効果）
- 固定ヘッダー
- アコーディオン式FAQ（Academy LP）
- お問い合わせフォーム（mailto実装）

## デザイン特徴

### コーポレートサイト（index.html）
- ヒーローセクション（フルスクリーン）
- 事業内容（2つのサービスカード）
- 代表紹介（写真 + プロフィール）
- 私たちの想い（背景画像付きセクション）
- 会社情報（テーブル形式）
- お問い合わせフォーム

### Academy LP（academy/index.html）
- 教育系らしい親しみやすいデザイン
- アクセントカラー: #DC2626
- 3ステップ説明
- 導入実績（レビューカード）
- FAQ（アコーディオン形式）
- 固定フッターCTA

## ロゴ実装

### ロゴ配置
- **coboaロゴ**: 全ページのヘッダー左側
- **coboa academyロゴ**: Academy LPヘッダー中央 + コーポレートサイト事業内容セクション

### ダークモード対策
```css
.dark-mode-safe {
    background: white;
    padding: 0.2rem 0.5rem;
    border-radius: 4px;
    display: inline-block;
}
```
- システムのダークモードでも黒字ロゴが見えるよう白背景で保護

### ロゴサイズ仕様
- **coboaロゴ**: height: 40px（メイン）/ 30px（Academy）
- **coboa academyロゴ**: height: 40px（統一）

## レスポンシブ対応

### ブレークポイント
- デスクトップ: 1200px以上
- タブレット: 768px - 1199px
- モバイル: 767px以下

### モバイル対応
- ハンバーガーメニュー
- カードレイアウトの1カラム化
- フォントサイズの調整（clamp使用）
- 固定フッターCTA（Academy LP）

## 問題解決記録

### ヘッダーロゴ配置問題
**問題**: 左のcoboaロゴと中央のacademyロゴの垂直位置がずれていた

**解決策**:
```css
.header-container {
    align-items: center; /* 全体の垂直中央揃え */
}

.logo {
    align-items: center; /* 左ロゴの垂直中央揃え */
}

.academy-title {
    line-height: 1;
    display: flex;
    align-items: center; /* アカデミーロゴの垂直中央揃え */
}

.header img {
    display: block;
    margin: 0;
    vertical-align: middle; /* 画像の垂直位置調整 */
}
```

### ダークモード対応
**問題**: システムのダークモードで黒字のロゴが見えなくなる

**解決策**: `.dark-mode-safe` クラスで白背景を適用し、黒字ロゴを保護

## お問い合わせ設定
- **メールアドレス**: contact@coboa-inc.com
- **実装方式**: mailto リンク
- **フォーム項目**: 名前、メールアドレス、件名、メッセージ

## デプロイ準備
- **プラットフォーム**: Vercel対応
- **画像**: プレースホルダー使用（実画像への差し替え待ち）
- **SEO**: meta description, title設定済み

## 今後の作業項目
1. **画像差し替え**
   - ヒーロー背景画像
   - 代表者写真
   - 陸上トラック写真（Academy LP）
   - 各背景画像

2. **実データ更新**
   - 導入実績の学校名・レビュー内容
   - FAQ の回答内容

3. **デプロイ**
   - Gitリポジトリにプッシュ
   - Vercelでデプロイ設定

## 開発環境
- **開発日**: 2025年7月23日
- **開発者**: Claude (Anthropic)
- **プロジェクト場所**: /mnt/c/Users/taiki/coboa/coboa-website

---
*このドキュメントは開発過程と設計思想を記録するために作成されました。*