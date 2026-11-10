# Once Upon a Voyage 🩵

ディズニーシー旅のしおり＋4人共有WALLET。静的サイトは GitHub Pages、リアルタイムの注文共有は Firebase Authentication（匿名）と Cloud Firestore を使います。

## 1. Firebaseを設定
1. https://console.firebase.google.com/ でプロジェクトを作成。
2. **Authentication → Sign-in method → 匿名** を有効化。
3. **Firestore Database** を作成（データベースのロケーションを選択）。「テストモード」のまま運用しないこと。
4. **Firestore Database → ルール** で `firestore.rules` の内容を貼り付け、**公開**する。
5. **プロジェクトの設定 → マイアプリ → Webアプリを追加**し、表示される `firebaseConfig` の値を `firebase-config.js` の `window.FIREBASE_CONFIG` に記入する。
6. Authentication → Settings → Authorized domains で GitHub Pages のドメインが必要に応じて許可されているか確認する。

## 2. GitHub Pagesで公開
1. GitHubで公開用リポジトリ（例 `our-magical-voyage`）を作る。
2. このフォルダ内の `index.html`, `app.js`, `firebase-config.js` をリポジトリの**ルート**にアップロード。`firestore.rules` と `README.md` は任意（公開してもよい）。
3. Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)` → Save。
4. 数分後に `https://ユーザー名.github.io/our-magical-voyage/` にアクセス。
5. WALLETの「招待URLをコピー」から**同じルームURL**を4人に共有。共有URLにはランダムな40桁のルームIDが付いています。

## 3. 動作確認
- PCとスマホなど別端末で**同じルームURL**を開く。
- 一方でテスト注文を追加 → もう一方にも反映されることを確認。
- 編集、削除、2人だけの割り勘、精算額を確認。
- Firebase設定前は**デモモード**で端末ごとの保存のみ。同期はされません。

## 注意
- 4人はGitHub/Firebaseのアカウント不要。ただし公開者はGitHubとFirebaseのアカウントが必要。
- **ルームURLを知っている人は誰でも注文を閲覧・編集できます**。URLは4人以外に送らず、SNSに載せないでください。これは厳格な4人限定ログインではなく「秘密のURL」方式です。
- FirebaseのWeb設定値は秘密鍵ではありません。**Firestoreルールが重要**です。匿名認証は利用者の実名確認ではありません。
- 無料枠には利用量の上限があり、状況によって課金や制限が発生する場合があります。利用プランを確認してください。
- 画像は権利上の問題を避けるため独自の夕暮れ風グラデーションを使用。ご自身の写真に差し替えることができます。
- 営業時間、ショーの公演有無、アトラクション運営状況は公式情報で当日確認してください。


## 2026-11-10 更新
- HOME表紙を `once-upon-a-voyage-cover.jpg` に変更。
- ミゲルズ(456)、テディ(429)の公式店舗URLを修正。ホライズンベイ(451)を追加。
- 11/17 ラウンドワンスタジアム前橋店でボウリング＆スポッチャを追加。
- 既存のWALLETとFirebase設定ファイルは維持。
- GitHubにアップロードする際はZIPそのものではなく、解凍後の6ファイルをリポジトリ直下に置いてください。


## 持ち物チェック（今回の更新）
- 各端末のブラウザの localStorage に保存されます。4人間では同期されません。
- 相川さん：ティッシュ、河野さん：ウェットティッシュ。常備薬は含めず寒さ対策のグッズを掲載。
- WALLETのリアルタイム同期は従来どおりFirebase設定・Firestoreルールの適用が必要です。
- GitHubの既存ファイルを更新する際は、同名ファイルを上書きする形でコミットしてください。
