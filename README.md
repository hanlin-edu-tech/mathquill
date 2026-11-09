## 使用情況調查（2026-11-09）

> 本節為 hanlin-edu-tech repo 清理作業的調查紀錄，待負責人確認後決定封存或刪除。

- 調查結論：仍在使用
- 建議處置：保留，理由：org 內 private repo `question-frame-api` 以 git 相依直接安裝本 fork，並打包本 fork 才有的建置產物，該 repo 近期仍有成功的正式環境部署。
- 最後更新：pushedAt 2020-10-05；最後 commit `890e1be8` 2020-10-05 Sparrow.jang Remove a build folder.
- 用途：上游 MathQuill 的 fork，相對上游只有 2 個自有 commit，內容是把 2020-09-14 版本的建置產物納入版控，供 org 內專案以 git 相依安裝；本身無部署。

### 檢查結果

| 檢查項目 | 結果 | 依據 |
|---|---|---|
| GitHub 活動 | 2020-10-05 後無 commit；相對上游只有 2 個自有 commit；無 PR、release、Actions | 已查核，細節記錄於內部調查報告 |
| org 內程式碼引用 | private repo `question-frame-api` 依賴本 fork；其他 repo 使用的是 npm registry 上的套件 | 已查核，細節記錄於內部調查報告 |
| GCP 部署 | 本 repo 無部署；依賴方正式環境部署近期成功 | 已查核，細節記錄於內部調查報告 |
| AWS 部署 | 查無 | 已查核，細節記錄於內部調查報告 |

### 待確認事項
- 本 fork 停在上游 2020-09-14 版本且大幅落後上游；需由 `question-frame-api` 負責人決定是否改用上游 npm 發佈版本，改用後本 fork 即可封存。
- 刪除本 fork 會使 `question-frame-api` 的安裝步驟失敗，處置前必須先完成上一項。

# [MathQuill](http://mathquill.com)

by [Han](http://github.com/laughinghan), [Jeanine](http://github.com/jneen), and [Mary](http://github.com/stufflebear) (<maintainers@mathquill.com>) [<img alt="slackin.mathquill.com" src="http://slackin.mathquill.com/badge.svg" align="top">](http://slackin.mathquill.com)

MathQuill is a web formula editor designed to make typing math easy and beautiful.

[<img alt="homepage demo" src="https://cloud.githubusercontent.com/assets/225809/15163580/1bc048c4-16be-11e6-98a6-de467d00cff1.gif" width="260">](http://mathquill.com)

The MathQuill project is supported by its [partners](http://mathquill.com/partners.html). We hold ourselves to a compassionate [Code of Conduct](http://docs.mathquill.com/en/latest/Code_of_Conduct/).

MathQuill is resuming active development and we're committed to getting things running smoothly. Find a dusty corner? [Let us know in Slack.](http://slackin.mathquill.com) (Prefer IRC? We're `#mathquill` on Freenode.)

## Getting Started

MathQuill has a simple interface. This brief example creates a MathQuill element and renders, then reads a given input:
```javascript
var htmlElement = document.getElementById('some_id');
var config = {
  handlers: { edit: function(){ ... } },
  restrictMismatchedBrackets: true
};
var mathField = MQ.MathField(htmlElement, config);

mathField.latex('2^{\\frac{3}{2}}'); // Renders the given LaTeX in the MathQuill field
mathField.latex(); // => '2^{\\frac{3}{2}}'
```

Check out our [Getting Started Guide](http://docs.mathquill.com/en/latest/Getting_Started/) for setup instructions and basic MathQuill usage.

## Docs

Most documentation for MathQuill is located on [ReadTheDocs](http://docs.mathquill.com/en/latest/).

Some older documentation still exists on the [Wiki](https://github.com/mathquill/mathquill/wiki).

## Open-Source License

The Source Code Form of MathQuill is subject to the terms of the Mozilla Public
License, v. 2.0: [http://mozilla.org/MPL/2.0/](http://mozilla.org/MPL/2.0/)

The quick-and-dirty is you can do whatever if modifications to MathQuill are in
public GitHub forks. (Other ways to publicize modifications are also fine, as
are private use modifications. See also: [MPL 2.0 FAQ](https://www.mozilla.org/en-US/MPL/2.0/FAQ/))
