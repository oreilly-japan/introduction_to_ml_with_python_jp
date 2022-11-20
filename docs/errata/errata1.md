---
layout: default
---

## 『Pythonではじめる機械学習』第1刷正誤表

下記の誤りがありました。お詫びして訂正いたします。

本ページに掲載されていない誤植など間違いを見つけた方は、japan＠oreilly.co.jpまで
お知らせください。

2017年7月12日更新


| 場所        | 誤     | 正   |
| :---------- | :--------- | :-------- |
|  p9、下から5行目 | `X = np.linspace(-10, 10, 100)` | `x = np.linspace(-10, 10, 100)` |
| p10、下から7行目 | `import pandas as pd` | `import pandas as pd`<br>`from IPython import display` |
| p17、下から13行目 |これらの数値の意味は、配列`iris[‘target_names’]` |これらの数値の意味は、配列`iris_dataset[‘target_names’]` |
| p141、下から3行目 | `# 最初の2つの主成分に対してデータポイントを変換`<br>`print("Original shape: {}".format(str(X_scaled.shape)))`<br>`print("Reduced shape: {}".format(str(X_pca.shape)))` | `# 最初の2つの主成分に対してデータポイントを変換`<br>`X_pca = pca.transform(X_scaled)`<br>`print("Original shape: {}".format(str(X_scaled.shape)))`<br>`print("Reduced shape: {}".format(str(X_pca.shape)))`|




