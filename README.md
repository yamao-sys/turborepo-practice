# turborepo-practice
Turborepoを使ってモノレポ管理してみる

Yarn Workspacesで以下が可能
- ライブラリの共通化
- 静的解析の共有
- ロジックの共通化
- ルートディレクトリから移動せずにコマンド実行

あとは以下2つができれば望ましく、他管理ツールを使う
- 変更のあったプロジェクトのみビルドできるように最適化
- 依存関係の可視化

他管理ツールのうち、Next.jsと相性が良さそうなTurborepoを検証(同じVercelが開発元なので)

※ NxはNext.jsで使うとバージョンアップ対応が煩わしいらしい

(https://tech.delm0.jp/entry/2023/05/29/161202)

※ ちなみにTurborepo公式ではpnpmを推奨しているもよう。ポリレポからモノレポに変えたいというタイミングでその企業で使用しているパッケージマネージャでWorkspacesを作ることになりそう。

とはいえ、複数プロジェクトでバージョンが揃っていない状況では、yarn classicではhoistする際にマジョリティのバージョンを選択してくれないことがあるらしい。

そうなると、yarn classicからyarn自体のバージョンを上げるのと、別のパッケージマネージャで作り直すのとでは工数感が変わらなさそうなので、pnpmへの移行も考えられそう。

(pnpmであれば、インストール速度やディスク容量の削減のメリットもあり、先述のようにTurborepoがpnpmを推奨しているので。)

## 参考
- https://zenn.dev/lancers/articles/3648d3b1752f51
- https://techblog.roxx.co.jp/entry/2022/08/08/130000
- https://techblog.roxx.co.jp/entry/2019/08/16/140000
- https://zenn.dev/moneyforward/articles/2645c956df1d26
