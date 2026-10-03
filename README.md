# otokumichi-data

オトクミチ（iOS アプリ。支払いとポイントの最適化）向けの公開配信データ。本体リポジトリ `pplog4/point-navigator` は private のため、GitHub Pages が匿名で読めるように共通データだけ分離している。

| パス | 用途 |
|---|---|
| `common-db/latest.json` | 最新の版を指す meta（schemaVersion・snapshotVersion・minimumAppVersion・publishedAt・contentHash(sha256)・bytes・path） |
| `common-db/v<版>.json` | 版ごとの共通データ本体（還元条件・キャンペーン・出典）。版別ファイルは消さない・上書きしない |

- 中身は本体の `npm run commondb:mirror` の出力をそのまま置く（手で編集しない）。出力前に二次情報ゲート（出典が公式でない行0件）を通す。
- 戻すときは `common-db/latest.json` だけを前の版へ向け直す。
- 還元率・条件は各社の公開情報をもとに登録したもので、各行に公式ページの出典を付けている。最新の条件は各社の公式ページで確認してほしい。
- 個人情報・認証情報は含めない。利用者の入力データはここに置かない（端末内のみ）。
