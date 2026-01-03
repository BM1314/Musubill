<!--
GENERATED FILE — DO NOT EDIT.
SSOT: /Spec.md
Run: powershell -ExecutionPolicy Bypass -File scripts/sync-spec.ps1
-->
# Musubill - ポートフォリオ自動生成アプリ 要件定義書（SSOT）

> **Version**: 1.0.0  
> **Last Updated**: 2025/01/04  
> **Author**: @Makhmeto_AI  
> **Development Method**: SDD（Specification-Driven Development）

---

## 1. プロダクト概要

### 1.1 プロダクト名
**Musubill**（むすびる）

### 1.2 コンセプト
「AIと一緒に、あなたの実績を"結ぶ"ポートフォリオ」

生成AIを活用して、副業やフリーランスを目指す人が簡単にプロフェッショナルなポートフォリオを作成できるWebアプリ。

### 1.3 ターゲットユーザー
@Makhmeto_AI のフォロワー層を中心に：

- **メインターゲット**: 20代の副業志望者・フリーランス志望者
- **サブターゲット**: 
  - IT業界への転職希望者
  - 生成AIを活用した副業に興味がある人
  - ノーコード/ローコードでWebサイトを作りたい人
  - クラウドソーシングで案件獲得を目指す人

### 1.4 解決する課題

| ユーザーの悩み | Musubillの解決策 |
|--------------|-----------------|
| ポートフォリオの作り方がわからない | AIがテンプレートと構成を提案 |
| デザインスキルがない | プロ品質のテンプレートを提供 |
| 何を載せればいいかわからない | AIが質問形式で必要情報を引き出す |
| 作成に時間がかかりすぎる | 最短10分で公開可能 |
| スマホで編集したい | Web & モバイル完全対応 |
| 無料で始めたい | フリープランで基本機能を提供 |

---

## 2. ユーザーストーリー

### 2.1 新規ユーザーの体験フロー

```
1. LP訪問 → 「10分で作れる」に惹かれる
2. 無料登録（メール or Google or GitHub）
3. AIとの対話形式で基本情報を入力
   - 職種・スキル・実績を質問形式で聞き取り
   - 「こんな感じですか？」とAIが要約を提示
4. テンプレート選択（3種類から）
5. プレビュー確認 → 調整
6. 公開！ 独自URLを取得
7. SNSでシェア
```

### 2.2 ユーザー目線の「こうだったらいいな」

#### 登録・認証
- [x] Googleアカウントで3秒ログインしたい
- [x] GitHubアカウントでも登録できると嬉しい（エンジニア向け）
- [x] メールアドレスでも登録できる選択肢が欲しい
- [x] パスワード忘れても簡単にリセットしたい

#### ポートフォリオ作成
- [x] AIと会話するだけで、自動的にセクションが埋まっていく
- [x] 「何を書けばいいかわからない」が解消される質問形式
- [x] スキルレベルを可視化するグラフが自動生成される
- [x] 実績の数字（売上、期間など）を入れると自動でハイライト
- [x] GitHub連携で、リポジトリ情報を自動インポートしたい
- [x] 画像をアップロードしたら自動でリサイズ・最適化

#### デザイン・テンプレート
- [x] シンプル / クリエイティブ / テクニカル の3系統は最低欲しい
- [x] カラーテーマを簡単に変更したい（5クリック以内）
- [x] ダークモード対応のテンプレート
- [x] フォントは読みやすい日本語フォント希望

#### 公開・共有
- [x] `musubill.app/username` のような覚えやすいURL
- [x] OGP画像が自動生成されて、SNSシェアで映える
- [x] QRコード生成（名刺に載せたい）
- [x] PDF出力もできると嬉しい（プロプラン）
- [x] 公開/非公開の切り替えがワンタップ

#### 編集・管理
- [x] スマホでサクッと実績追加したい
- [x] プレビューを見ながらリアルタイム編集
- [x] ドラッグ&ドロップでセクション並び替え
- [x] 変更履歴が見れると安心
- [x] 一時保存（下書き）機能

#### 分析
- [x] どれくらい見られてるか数字で知りたい
- [x] どのセクションがよく読まれているか知りたい
- [x] 訪問者の地域・デバイス情報

#### 課金（Stripe必須）
- [x] 無料で十分試せる
- [x] 月額払いと年額払いの選択肢
- [x] いつでも解約できる安心感
- [x] プラン変更がスムーズ

---

## 3. 機能要件

### 3.1 料金プラン

| 機能 | Free | Pro (¥980/月) | Business (¥2,980/月) |
|-----|------|--------------|---------------------|
| ポートフォリオ数 | 1 | 5 | 無制限 |
| AIアシスト生成 | 月3回 | 月50回 | 無制限 |
| テンプレート | 3種類 | 10種類 | 全種類 + カスタム |
| 独自ドメイン | - | ✓ | ✓ |
| PDF出力 | - | ✓ | ✓ |
| アクセス解析 | 基本 | 詳細 | 高度 |
| 優先サポート | - | ✓ | ✓ |
| チームコラボ | - | - | ✓ |
| 広告非表示 | - | ✓ | ✓ |

### 3.2 MVP機能（Phase 1）

#### 認証・ユーザー管理
- [ ] Email/Password認証
- [ ] Google OAuth 2.0
- [ ] GitHub OAuth
- [ ] パスワードリセット
- [ ] プロフィール編集
- [ ] アカウント削除（GDPR対応）

#### ポートフォリオ作成
- [ ] AI対話形式の情報入力
- [ ] 基本テンプレート3種類
- [ ] セクション管理（追加・編集・削除・並び替え）
- [ ] 画像アップロード（プロフィール画像、実績画像）
- [ ] リアルタイムプレビュー
- [ ] 自動保存

#### 公開・共有
- [ ] 公開URL発行（`musubill.app/{username}`）
- [ ] 公開/非公開切り替え
- [ ] OGP画像自動生成
- [ ] QRコード生成

#### 決済（Stripe）
- [ ] サブスクリプション登録
- [ ] プラン変更
- [ ] 解約
- [ ] 請求書・領収書表示
- [ ] Webhook処理

### 3.3 Phase 2機能

- [ ] GitHub連携（リポジトリ自動インポート）
- [ ] PDF出力
- [ ] アクセス解析ダッシュボード
- [ ] 追加テンプレート
- [ ] カスタムドメイン対応

### 3.4 Phase 3機能

- [ ] チーム機能
- [ ] AIによる改善提案
- [ ] A/Bテスト機能
- [ ] 多言語対応（英語）

---

## 4. 技術要件

### 4.1 技術スタック（確定）

#### フロントエンド
| 項目 | 技術選定 | 理由 |
|-----|---------|-----|
| フレームワーク | **React 18** + **TypeScript** | 型安全性、エコシステム、Cursor対応 |
| ビルドツール | **Vite** | 高速ビルド、HMR |
| スタイリング | **Tailwind CSS** | 高速開発、一貫性 |
| UIライブラリ | **shadcn/ui** | カスタマイズ性、アクセシビリティ |
| 状態管理 | **Zustand** | シンプル、軽量 |
| データフェッチ | **TanStack Query** | キャッシュ、リアルタイム更新 |
| フォーム | **React Hook Form** + **Zod** | バリデーション、型安全 |
| アニメーション | **Framer Motion** | 滑らかなUI |
| エディタ | **Tiptap** | リッチテキスト編集 |
| D&D | **dnd-kit** | ドラッグ&ドロップ |

#### バックエンド
| 項目 | 技術選定 | 理由 |
|-----|---------|-----|
| フレームワーク | **FastAPI** | 非同期、自動ドキュメント、型安全 |
| 言語 | **Python 3.11+** | AI連携の容易さ、エコシステム |
| ORM | **SQLAlchemy 2.0** + **Alembic** | 型安全、マイグレーション |
| 認証 | **FastAPI-Users** | OAuth対応、JWT |
| バリデーション | **Pydantic v2** | 高速、型安全 |
| タスクキュー | **Celery** + **Redis** | 非同期処理 |
| AI連携 | **Anthropic Claude API** | 日本語精度、対話型 |

#### インフラ・デプロイ
| 項目 | 技術選定 | 理由 |
|-----|---------|-----|
| フロントエンド | **Vercel** | 自動デプロイ、エッジ最適化 |
| バックエンド | **Railway** | Pythonサポート、スケーリング |
| データベース | **Railway PostgreSQL** | マネージドDB |
| Redis | **Railway Redis** | セッション、キャッシュ |
| ストレージ | **Cloudflare R2** | S3互換、低コスト |
| CDN | **Cloudflare** | 高速配信 |
| ドメイン | **Cloudflare Registrar** | 統合管理 |

#### 外部サービス
| 項目 | サービス | 用途 |
|-----|---------|-----|
| 決済 | **Stripe** | サブスクリプション（必須） |
| メール | **Resend** | トランザクショナルメール |
| モニタリング | **Sentry** | エラー追跡 |
| 分析 | **PostHog** or **Plausible** | プライバシー配慮 |
| AI | **Anthropic Claude API** | ポートフォリオ生成 |
| 画像処理 | **Sharp (Node)** or **Pillow** | リサイズ・最適化 |
| PDF生成 | **WeasyPrint** | PDF出力 |
| QRコード | **qrcode (Python)** | QR生成 |

### 4.2 ディレクトリ構成

```
musubill/
├── frontend/                 # React (Vercel)
│   ├── src/
│   │   ├── components/       # UIコンポーネント
│   │   │   ├── ui/          # shadcn/ui
│   │   │   ├── portfolio/   # ポートフォリオ関連
│   │   │   ├── editor/      # エディタ関連
│   │   │   └── layout/      # レイアウト
│   │   ├── pages/           # ページコンポーネント
│   │   ├── hooks/           # カスタムフック
│   │   ├── stores/          # Zustand stores
│   │   ├── services/        # API通信
│   │   ├── types/           # TypeScript型定義
│   │   ├── utils/           # ユーティリティ
│   │   └── styles/          # グローバルスタイル
│   ├── public/
│   └── package.json
│
├── backend/                  # FastAPI (Railway)
│   ├── app/
│   │   ├── api/
│   │   │   ├── v1/
│   │   │   │   ├── auth/
│   │   │   │   ├── users/
│   │   │   │   ├── portfolios/
│   │   │   │   ├── subscriptions/
│   │   │   │   └── ai/
│   │   │   └── deps.py
│   │   ├── core/
│   │   │   ├── config.py
│   │   │   ├── security.py
│   │   │   └── database.py
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── services/
│   │   │   ├── ai_service.py
│   │   │   ├── stripe_service.py
│   │   │   └── storage_service.py
│   │   ├── tasks/            # Celeryタスク
│   │   └── main.py
│   ├── alembic/              # マイグレーション
│   ├── tests/
│   └── requirements.txt
│
└── docs/                     # ドキュメント
    ├── api/
    └── design/
```

### 4.3 データベース設計

```sql
-- ユーザーテーブル
CREATE TABLE users (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    email VARCHAR(255) UNIQUE NOT NULL,
    hashed_password VARCHAR(255),
    display_name VARCHAR(100),
    avatar_url VARCHAR(500),
    provider VARCHAR(20),  -- 'email', 'google', 'github'
    provider_id VARCHAR(255),
    stripe_customer_id VARCHAR(255),
    subscription_status VARCHAR(20) DEFAULT 'free',
    subscription_plan VARCHAR(20) DEFAULT 'free',
    is_active BOOLEAN DEFAULT true,
    is_verified BOOLEAN DEFAULT false,
    created_at TIMESTAMPTZ DEFAULT NOW(),
    updated_at TIMESTAMPTZ DEFAULT NOW()
);

-- ポートフォリオテーブル
CREATE TABLE portfolios (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID REFERENCES users(id) ON DELETE CASCADE,
    slug VARCHAR(100) UNIQUE NOT NULL,
    title VARCHAR(200) NOT NULL,
    description TEXT,
    template_id VARCHAR(50) NOT NULL,
    color_theme JSONB DEFAULT '{}',
    is_published BOOLEAN DEFAULT false,
    published_at TIMESTAMPTZ,
    view_count INTEGER DEFAULT 0,
    meta_data JSONB DEFAULT '{}',
    created_at TIMESTAMPTZ DEFAULT NOW(),
    updated_at TIMESTAMPTZ DEFAULT NOW()
);

-- セクションテーブル
CREATE TABLE sections (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    portfolio_id UUID REFERENCES portfolios(id) ON DELETE CASCADE,
    type VARCHAR(50) NOT NULL,  -- 'profile', 'skills', 'projects', 'experience', 'contact'
    title VARCHAR(200),
    content JSONB NOT NULL,
    sort_order INTEGER NOT NULL,
    is_visible BOOLEAN DEFAULT true,
    created_at TIMESTAMPTZ DEFAULT NOW(),
    updated_at TIMESTAMPTZ DEFAULT NOW()
);

-- 画像テーブル
CREATE TABLE images (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID REFERENCES users(id) ON DELETE CASCADE,
    portfolio_id UUID REFERENCES portfolios(id) ON DELETE SET NULL,
    original_url VARCHAR(500) NOT NULL,
    thumbnail_url VARCHAR(500),
    file_size INTEGER,
    mime_type VARCHAR(50),
    created_at TIMESTAMPTZ DEFAULT NOW()
);

-- サブスクリプション履歴
CREATE TABLE subscription_history (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID REFERENCES users(id) ON DELETE CASCADE,
    stripe_subscription_id VARCHAR(255),
    plan VARCHAR(20) NOT NULL,
    status VARCHAR(20) NOT NULL,
    current_period_start TIMESTAMPTZ,
    current_period_end TIMESTAMPTZ,
    created_at TIMESTAMPTZ DEFAULT NOW()
);

-- アクセスログ
CREATE TABLE portfolio_views (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    portfolio_id UUID REFERENCES portfolios(id) ON DELETE CASCADE,
    visitor_ip VARCHAR(45),
    user_agent TEXT,
    referer VARCHAR(500),
    country VARCHAR(2),
    device_type VARCHAR(20),
    viewed_at TIMESTAMPTZ DEFAULT NOW()
);
```

### 4.4 API設計（主要エンドポイント）

```yaml
# 認証
POST   /api/v1/auth/register          # メール登録
POST   /api/v1/auth/login             # ログイン
POST   /api/v1/auth/logout            # ログアウト
POST   /api/v1/auth/refresh           # トークン更新
POST   /api/v1/auth/reset-password    # パスワードリセット
GET    /api/v1/auth/google            # Google OAuth
GET    /api/v1/auth/github            # GitHub OAuth

# ユーザー
GET    /api/v1/users/me               # 自分の情報
PATCH  /api/v1/users/me               # プロフィール更新
DELETE /api/v1/users/me               # アカウント削除

# ポートフォリオ
GET    /api/v1/portfolios             # 一覧取得
POST   /api/v1/portfolios             # 新規作成
GET    /api/v1/portfolios/{id}        # 詳細取得
PATCH  /api/v1/portfolios/{id}        # 更新
DELETE /api/v1/portfolios/{id}        # 削除
POST   /api/v1/portfolios/{id}/publish    # 公開
POST   /api/v1/portfolios/{id}/unpublish  # 非公開

# セクション
GET    /api/v1/portfolios/{id}/sections       # 一覧
POST   /api/v1/portfolios/{id}/sections       # 追加
PATCH  /api/v1/sections/{id}                  # 更新
DELETE /api/v1/sections/{id}                  # 削除
POST   /api/v1/portfolios/{id}/sections/reorder  # 並び替え

# AI
POST   /api/v1/ai/generate-content    # コンテンツ生成
POST   /api/v1/ai/suggest-skills      # スキル提案
POST   /api/v1/ai/improve-text        # テキスト改善

# 画像
POST   /api/v1/images/upload          # アップロード
DELETE /api/v1/images/{id}            # 削除

# サブスクリプション (Stripe)
POST   /api/v1/subscriptions/checkout    # チェックアウト開始
POST   /api/v1/subscriptions/portal      # カスタマーポータル
GET    /api/v1/subscriptions/status      # 状態確認
POST   /api/v1/webhooks/stripe           # Stripe Webhook

# 公開ポートフォリオ（認証不要）
GET    /api/v1/public/{username}         # 公開ページ取得
POST   /api/v1/public/{username}/view    # 閲覧記録
```

### 4.5 環境変数

```env
# Frontend (.env)
VITE_API_URL=https://api.musubill.app
VITE_STRIPE_PUBLIC_KEY=pk_live_xxx

# Backend (.env)
# App
APP_ENV=production
SECRET_KEY=your-secret-key
FRONTEND_URL=https://musubill.app

# Database
DATABASE_URL=postgresql://user:pass@host:5432/musubill

# Redis
REDIS_URL=redis://localhost:6379

# OAuth
GOOGLE_CLIENT_ID=xxx
GOOGLE_CLIENT_SECRET=xxx
GITHUB_CLIENT_ID=xxx
GITHUB_CLIENT_SECRET=xxx

# Stripe
STRIPE_SECRET_KEY=sk_live_xxx
STRIPE_WEBHOOK_SECRET=whsec_xxx
STRIPE_PRICE_PRO_MONTHLY=price_xxx
STRIPE_PRICE_PRO_YEARLY=price_xxx
STRIPE_PRICE_BUSINESS_MONTHLY=price_xxx
STRIPE_PRICE_BUSINESS_YEARLY=price_xxx

# Cloudflare R2
R2_ACCESS_KEY_ID=xxx
R2_SECRET_ACCESS_KEY=xxx
R2_BUCKET_NAME=musubill-uploads
R2_ENDPOINT=https://xxx.r2.cloudflarestorage.com

# AI
ANTHROPIC_API_KEY=sk-ant-xxx

# Email
RESEND_API_KEY=re_xxx

# Monitoring
SENTRY_DSN=https://xxx@sentry.io/xxx
```

---

## 5. セキュリティ要件

### 5.1 認証・認可
- JWT + Refresh Token方式
- トークン有効期限: Access 15分 / Refresh 7日
- HTTPS必須
- CORS設定（許可オリジン限定）

### 5.2 データ保護
- パスワードは bcrypt でハッシュ化
- 機密データは暗号化して保存
- SQLインジェクション対策（ORM使用）
- XSS対策（React自動エスケープ + CSP）

### 5.3 決済セキュリティ
- カード情報は Stripe が管理（PCI DSS準拠）
- Webhook署名検証必須
- 二重課金防止（idempotency key）

### 5.4 レート制限
- API: 100 req/min per user
- AI生成: プランごとに制限
- 画像アップロード: 10 req/min

---

## 6. 非機能要件

### 6.1 パフォーマンス
- 初回ロード: 3秒以内（LCP）
- API応答: 500ms以内
- 画像最適化: WebP + lazy load

### 6.2 可用性
- SLA: 99.9%
- 自動スケーリング（Railway）
- ヘルスチェック実装

### 6.3 スケーラビリティ
- 初期想定: 1,000 MAU
- 6ヶ月目標: 10,000 MAU
- 水平スケーリング可能な設計

---

## 7. 開発ロードマップ

### Phase 1: MVP（4週間）
- Week 1: 環境構築、認証、DB設計
- Week 2: ポートフォリオCRUD、テンプレート
- Week 3: AI連携、Stripe連携
- Week 4: テスト、デプロイ、バグ修正

### Phase 2: 成長（4週間）
- GitHub連携
- PDF出力
- アクセス解析

### Phase 3: 拡張（4週間）
- チーム機能
- カスタムドメイン
- 多言語対応

---

## 8. 成功指標（KPI）

| 指標 | 1ヶ月目標 | 3ヶ月目標 | 6ヶ月目標 |
|-----|----------|----------|----------|
| 登録ユーザー数 | 100 | 500 | 2,000 |
| 有料転換率 | 3% | 5% | 8% |
| MRR | ¥3万 | ¥25万 | ¥100万 |
| チャーン率 | - | <10% | <5% |
| NPS | - | 30+ | 50+ |

---

## 9. リスクと対策

| リスク | 影響度 | 対策 |
|-------|-------|-----|
| AIコスト増大 | 高 | 使用量制限、キャッシュ活用 |
| 競合出現 | 中 | 差別化機能の早期開発 |
| Stripeトラブル | 高 | 決済エラーハンドリング強化 |
| サーバーダウン | 高 | マルチリージョン検討 |

---

## 10. 参考リンク

- [FastAPI公式](https://fastapi.tiangolo.com/)
- [React公式](https://react.dev/)
- [Stripe Subscriptions](https://stripe.com/docs/billing/subscriptions)
- [Vercelデプロイ](https://vercel.com/docs)
- [Railwayデプロイ](https://docs.railway.app/)
- [Anthropic Claude API](https://docs.anthropic.com/)

---

## 更新履歴

| 日付 | バージョン | 変更内容 |
|-----|-----------|---------|
| 2025/01/04 | 1.0.0 | 初版作成 |

