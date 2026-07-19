# claude-plugins

roamer7038 の Claude Code プラグインを集約したマーケットプレイス（カタログ）。個々のプラグインは各自のリポジトリで管理され、このリポジトリはそれらを `.claude-plugin/marketplace.json` で参照するだけである。

## 使い方

一度だけマーケットプレイスを登録すれば、収録プラグインをまとめて導入できる。

リポジトリ名は `claude-plugins` だが、マーケットプレイス名（`plugin@marketplace` で使う識別子）は `roamer7038-plugins`。

```
/plugin marketplace add roamer7038/claude-plugins
/plugin install kg-wiki@roamer7038-plugins
/plugin install notify-hook-plugin@roamer7038-plugins
```

最新へ更新するには次を実行する（各プラグインの default ブランチを追従する）。

```
/plugin marketplace update roamer7038-plugins
```

## 収録プラグイン

| プラグイン | リポジトリ | 概要 |
|---|---|---|
| `kg-wiki` | [kg-wiki-plugin](https://github.com/roamer7038/kg-wiki-plugin) | Markdown 知識リポジトリ + 派生 KG による知識管理 |
| `notify-hook-plugin` | [notify-hook-plugin](https://github.com/roamer7038/notify-hook-plugin) | WSL から Windows トースト通知を出すフック |

## プラグインを追加する

`.claude-plugin/marketplace.json` の `plugins` 配列に、リポジトリを指す `source` を追記する。

```json
{
  "name": "<plugin 名>",
  "source": { "source": "github", "repo": "roamer7038/<repo>" }
}
```
