# Layered Architecture
## 概要
Layerを技術的な関心事ごとに分割する

- controller: usecaseと外の世界をつなぐ
- usecase: ビジネスロジックとそれに関連するシステムの取り決めを司る
- reposiroty: データを永続する

処理の流れ
1. controller
2. usecase
3. reposiroty

依存関係
- 依存関係を考えるに際して、どの層が相対的に変更されにくいのかを考える
- 変更されにいくいのはビジネス要件を含むusecase層となる
- 変更されにくい層(usecase)に、変更されやすい層(repository, controller)が依存するべき

Layered Architectureの3層はシステムの方針と詳細に分類できる。

依存関係を適切に守っていれば、以下のようなことが可能になるはず
- reposiroty層の実態をデータベースからRedisに変更する際、usecase層を変更する必要はない
- controller層が繋ぐ外の世界が、Webからターミナルに変わってもusecase層を変更する必要はない

