# Rei Landing Page

## プロジェクト概要

Rei（@Rei_value）公式LP。観測軸ブランドの「玄関」。
Xプロフィール url 先・noteリンク集約・観測中のプロジェクト紹介を1ページに集約する。

## ブランド方針（最重要）

- **記録軸 / 観測軸**：「当たる/外れる/的中率」評価軸は使わない
- **予測示唆・売買推奨はしない**：ポケカ・株式いずれも
- **数字の公開ポリシー**：絶対数は静的（観測N・テスト数等のメタ情報のみ）、X投稿KPIは前週比%のみ
- **透明性をブランドにする**：cron数・テスト本数・観測N まで開示

詳細は `Projects/docs/Rei-Brand-Guidelines.md`（正本）を参照。

## NG表現（出力に含めない）

- 的中・精度・勝率・正解率・買い時・読む・絶対・儲かる
- 「Claude」直名（「AI」と表記）
- 結果訴求型コピー（「月100万」「会社作れる」等）

## 技術スタック

- フレームワーク：なし（vanilla HTML）
- スタイル：vanilla CSS（プリプロセッサなし）
- フォント：Noto Sans JP + JetBrains Mono（Google Fonts）
- デプロイ：GitHub Pages or Cloudflare Pages（無料）

ビルドステップ不要。`index.html` をブラウザで直接開いて開発できる。

## カラーパレット（observatory tone）

- ベース：オフホワイト `#FAFAF7` × ダークグレー `#1F2937`
- アクセント：muted teal `#2C7A7B`（観測者の青緑）
- データ強調：teal soft `#E6F4F4` / mono font

## セクション構造

1. Header（fixed, minimal）
2. Hero（観測する人。数字を出す側になる。）
3. 観測中の指標（stats grid · 静的）
4. 動いているプロジェクト（projects grid · 4枚）
5. note記事ショーケース（2枚）
6. About Rei（4 principles）
7. Footer（X / note / GitHub）

## 数字の更新ルール

「観測中の指標」セクションの数字は手動更新。
更新タイミング：
- 予測ログN：週1回（日曜の cron 完了後）
- 公開note：新規公開時のみ
- テスト本数：節目（+10本以上の増加時）
- 稼働cron：cron追加・削除時

将来的に：観測日誌cronから static JSON を吐いて自動更新する仕組みも検討。

## Workflow

### Start Every Session

1. **Plan first** — 実装前に必ず設計を出す
2. **Clarify ambiguity** — 不明点は先に確認
3. **Context management** — 50%到達で /compact

### Development

- 小さなコミット（1機能1コミット）
- コミットメッセージ日本語OK
- squash merge

## Git Practices

```
feat: hero セクションのコピー更新
fix: モバイル時のCTAボタン余白修正
style: アクセント色の調整
chore: OGP メタタグ追加
```

## Code Standards

- 無駄な抽象化はしない（vanilla HTMLの利点を活かす）
- 未来のための予防コード禁止
- 入力境界（URL・OGP）のみバリデーション

## Self-Serve Setup

```bash
# 開発：ブラウザで index.html を直接開く
# または簡易サーバー
python -m http.server 8080
# → http://localhost:8080
```

## デプロイ計画（未実施）

- 候補1：GitHub Pages（github.io/landing-page）
- 候補2：Cloudflare Pages（独自ドメイン rei.dev 等を将来取得）
- まずは GitHub Pages で動かして、Xプロフィール url を差し替える

## よく参照するファイル

- `index.html` — 全コンテンツ
- `css/theme.css` — カラー・タイポ・スペーシング変数
- `css/style.css` — レイアウト本体
- `../../docs/Rei-Brand-Guidelines.md` — Reiトーンの正本
