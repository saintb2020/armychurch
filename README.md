# ARMY CHURCH サイト v1 — 公開手順

## 中身
- `index.html` — サイト本体（1ファイル完結）
- `assets/logo-emblem.jpg` — ヒーロー背景（エンブレム）
- `assets/logo-lockup.jpg` — OGP画像・動画ポスター（ロゴ＋文字）

## 公開手順（実働30分）

### そもそも何をするのか
サイトは「ファイルの束」でしかない。世界中の人が見られるようにするには、ファイルをインターネット上の置き場（サーバー）に載せる必要がある。Wixは「作る道具＋置き場」がセットだったが、今回はClaudeが作ったファイルを**Netlify（ネットリファイ）という無料の置き場**に載せる。作業はフォルダを画面に放り込むだけ。

### 手順
1. Claudeからダウンロードした `armychurch_v1.zip` をPCで解凍する（ダブルクリック）→ `armychurch` というフォルダができる
2. ブラウザで **app.netlify.com/drop** を開く（Googleアカウントで無料登録できる）
3. 画面に「Drag and drop your site folder here」という枠がある → そこに手順1の `armychurch` フォルダをそのまま放り込む
4. 数秒で `xxxx.netlify.app` という仮のURLが発行され、**その瞬間からサイトは全世界に公開されている**。スマホでそのURLを開けば確認できる
5. 仮URLのままではダサいので、独自ドメインを繋ぐ：Netlifyの管理画面 → Domain settings → `armychurch.jp` を追加 → 画面に表示されるDNS設定値を、armychurch.jpを買ったサービス（お名前.com等）の管理画面にコピペする
6. SSL（httpsの鍵マーク）は自動で付く（数分〜数時間待つだけ）

修正したくなったら：Claudeに修正させた新しいフォルダを、同じNetlifyの画面（Deploys）にまた放り込むだけで上書き公開される。

## rabu.church からのリダイレクト（AEO資産の引き継ぎ）
- Wix管理画面 → 設定 → 「301リダイレクト」→ `rabu.church/*` → `https://armychurch.jp/` を設定
- **Wixの契約は数ヶ月維持**（リダイレクトを生かすため）。検索・AIの評価が新ドメインに移ってから解約

## 公開後にやること
1. **動画**：雰囲気動画を `assets/inside.mp4` という名前で置いて再アップロード → 自動で再生される（置くまではロゴ表示のみ。このまま公開してOK）
2. **証しの写真**：現在はrabu.churchのWix画像を直接読み込んでいる。**Wix解約前に必ず**元画像をダウンロードし、`assets/` に置いて `index.html` の該当URLを差し替えること（解約すると画像が消える）
3. **Instagram**：フッターとINFOのリンクが現在 `@rabu.church`。アカウント名を変更したらURLを差し替え
4. **Googleビジネスプロフィール**：ARMY CHURCH名義で登録（または既存RABUの名称変更）。MEOはこれが本体
5. **Search Console**：armychurch.jpを登録してインデックス申請

## 構造化データ（実装済み）
- `Church`スキーマ（住所・営業時間・無料・対応言語）
- `FAQPage`スキーマ（FAQ8問）— AEO/リッチリザルト対応
