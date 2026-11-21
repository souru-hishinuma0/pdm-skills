# PdM Skills

Senior PdMが業務で使う思考の型（戦略ほか）を、AIエージェント（Claude Code、Claude.ai などのskill対応環境）から呼び出せる skill としてまとめたリポジトリです。

## 収録skill

| skill | 用途 |
|---|---|
| [strategy-pattern-recognition](skills/strategy-pattern-recognition/SKILL.md) | 症状から定石パターンを照合し、仮説・検証観点・打ち手を出す（B2B SaaS／AIプロダクト） |

今後、戦略以外の領域も含めて skill を追加予定です。

## 使い方

### Claude Code（プラグインとして）
```
/plugin marketplace add souru-hishinuma0/pdm-skills
/plugin install pdm-skills@pdm-skills
```

### Claude.ai などにskillとして追加
`skills/<skill名>/` フォルダをzipにしてアップロードします。

### 呼び出し例
> 競合が当社の主要機能を無料で標準搭載すると発表した。戦略パターン認識で整理して。

## 構成

```
.claude-plugin/
  plugin.json         プラグイン定義
  marketplace.json    マーケットプレイス定義
skills/
  strategy-pattern-recognition/
    SKILL.md          手順と出力フォーマット
    references/       領域別のパターン集とテンプレート
```

## 設計の考え方
- パターンは結論ではなく仮説の供給源。必ず反証シグナルとセットで使う
- 勝てる戦略 ＝ 定石 ＋ インサイト。skillは定石を速く引き出し、インサイトのための問いを残す
- 定石から始め、自分の経験から得たパターンを育てていく（`references/_template.md`）

## 参考
- 御立尚資『戦略「脳」を鍛える』（東洋経済新報社）のコンセプトワード整理を出発点に、PdM向け・現代の競争環境向けに再構成しています。

## ライセンス
[MIT](LICENSE)
