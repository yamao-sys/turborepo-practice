# yarn-turborepo-practice
Yarn Workspaces × Turborepoを使ってモノレポ管理してみる

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

[参考](https://hack.nikkei.com/blog/advent20241212/#:~:text=%E3%82%89%E3%81%84%E3%81%BE%E3%81%97%E3%81%9F%E3%80%82-,%E3%83%A2%E3%83%8E%E3%83%AC%E3%83%9D%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E3%83%91%E3%83%83%E3%82%B1%E3%83%BC%E3%82%B8%E3%83%9E%E3%83%8D%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC%E3%81%AE%E8%AA%B2%E9%A1%8C,-%E3%83%A2%E3%83%8E%E3%83%AC%E3%83%9D%E3%81%AE)

そうなると、yarn classicからyarn自体のバージョンを上げるのと、別のパッケージマネージャで作り直すのとでは工数感が変わらなさそうなので、pnpmへの移行も考えられそう。

(pnpmであれば、インストール速度やディスク容量の削減のメリットもあり、先述のようにTurborepoがpnpmを推奨しているので。)

## 参考
- https://zenn.dev/lancers/articles/3648d3b1752f51
- https://techblog.roxx.co.jp/entry/2022/08/08/130000
- https://techblog.roxx.co.jp/entry/2019/08/16/140000
- https://zenn.dev/moneyforward/articles/2645c956df1d26
- https://zenn.dev/glassonion1/articles/734b8db0f5a47e
