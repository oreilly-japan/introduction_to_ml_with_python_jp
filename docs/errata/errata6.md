---
layout: default
---
## 『Pythonではじめる機械学習』第6刷正誤表

下記の誤りがありました。お詫びして訂正いたします。

本ページに掲載されていない誤植など間違いを見つけた方は、japan＠oreilly.co.jpまで
お知らせください。

2019年5月更新


| 場所        | 誤     | 正   |
| :---------- | :--------- | :-------- |
| pviii、2行目 | IPythonノートブック | Jupyter Notebook
| p10、In[6]:の1-2行目 | `import pandas as pd`<br>`from IPython import display` | `import pandas as pd`|


p13、Out[8]:差し替え<br>
【誤】
```python
Python version: 3.5.2 |Anaconda 4.1.1 (64-bit)| (default, Jul 2 2016, 17:53:06)
[GCC 4.4.7 20120313 (Red Hat 4.4.7-1)]
pandas version: 0.18.1
matplotlib version: 1.5.1
NumPy version: 1.11.1
SciPy version: 0.17.1
IPython version: 5.1.0
scikit-learn version: 0.18
```
【正】
```python
Python version: 3.6.1 |Continuum Analytics, Inc.| (default, May 11 2017, 13:04:09)
[GCC 4.2.1 Compatible Apple LLVM 6.0 (clang-600.0.57)]
pandas version: 0.24.2
matplotlib version: 3.0.3
NumPy version: 1.16.3
SciPy version: 1.2.1
IPython version: 6.5.0
scikit-learn version: 0.20.3
```

| 場所        | 誤     | 正   |
| :---------- | :--------- | :-------- |
| p13、サソリの1行目 | 0.18 | 0.20|
| p29、5行目 | つけない | 付けない
| p29、表2-1下の1行目| 45歳 | 45才|
| p29、下から4行目 | 考えついた | 考え付いた|
| p30、2行目 | 50歳 | 50才|
| p31、7行目 | 45歳 | 45才|
| p40、1行目 | 全く | まったく|
| p54、17行目 | 度合 | 度合い|
| p57、2行目 | 図る | 測る|
| p61、サソリの最終行 | つば | ツバ|
| p72、下から7行目 | 行っていることなる。 | 行っていることになる。|
| p73、下から10行目 | 重視すぎて | 重視しすぎて|
| p86、下から10行目 | 補なって | 補って|
| p105、1行目 | 図2-39 | 図2-45|
| p113、図2-54 | 重み行列の例 | 重み行列の列|
| p129、下から8行目 | 平均値の | 平均値と|
| p147、下から8行目 | 代わって | 変わって|
| p153、6行目 | 原点（0, 0) | 原点(0, 0)|
| p185、下から3行目 | 取扱 | 取り扱い|
| p190、12行目 | 興味のあるものになっているかは、 | ユーザにとって興味深いものになっていることを確認するには、|
| p203、12行目 | 納めれば | 収めれば|
| p206、表4-1の注釈 | hours-per-week、occupation：週あたりの労働時間 | hours-per-week：週あたりの労働時間、occupation：職業|
| p208、In[1]:の1行目 | `import pandas as pd` | `import pandas as pd`<br>`import os`|
| p208、表4-3の注釈 | hours-per-week、occupation：週あたりの労働時間 | hours-per-week：週あたりの労働時間、occupation：職業|

p223、下から1-2行目<br>
【誤】
```python
X_train, X_test, y_train, y_test = train_test_split
    (boston.data, boston.target, random_state=0)
```
【正】
```python
X_train, X_test, y_train, y_test = train_test_split(
    boston.data, boston.target, random_state=0)
```

p238、In[51]:<br>
【誤】
```python
# ターゲット値（レンタル数）を抽出
y = citibike.values
# 時刻を"%s"でPOSIX時刻に変換
X = citibike.index.astype("int64").reshape(-1, 1) // 10**9
```
【正】
```python
# ターゲット値（レンタル数）を抽出
y = citibike.values
# 10**9 で割ってPOSIX時刻に変換
X = citibike.index.astype("int64").to_numpy().reshape(-1, 1) // 10**9
```

p.239、下から2行目<br>
【誤】
```python
X_hour = citibike.index.hour.reshape(-1, 1)
```
【正】
```python
X_hour = citibike.index.hour.to_numpy().reshape(-1, 1)
```

p240、In[55]:の1-2行目<br>
【誤】
```python
X_hour_week = np.hstack([citibike.index.dayofweek.reshape(-1, 1),
                         citibike.index.hour.reshape(-1, 1)])
```
【正】
```python
X_hour_week = np.hstack([citibike.index.dayofweek.to_numpy().reshape(-1, 1),
                         citibike.index.hour.to_numpy().reshape(-1, 1)])
```

| 場所        | 誤     | 正   |
| :---------- | :--------- | :-------- |
| p248、7行目 | はいって | 入って
| p254、In[16]: | `mglearn.plots.plot_label_kfold()` | `mglearn.plots.plot_group_kfold()`|
| p254、図5-4 | LabelKFold | GroupKFold|
| p268、3行目 | 手続 | 手続き|

p281、In[51]:の2-3行目<br>
【誤】
```python
X, y = make_blobs(n_samples=(400, 50), centers=2, cluster_std=[7.0, 2],
                  random_state=22) 
```
【正】
```python
X, y = make_blobs(n_samples=(400, 50), cluster_std=[7.0, 2], random_state=22)
```
| 場所        | 誤     | 正   |
| :---------- | :--------- | :-------- |
| p283、下から2行目 | すべての | すべてを|

p284、In[57]:の2-3行目<br>
【誤】
```python
X, y = make_blobs(n_samples=(4000, 500), centers=2, cluster_std=[7.0, 2],
                  random_state=22) 
```
【正】
```python
X, y = make_blobs(n_samples=(4000, 500), cluster_std=[7.0, 2], random_state=22)
```


p284、In[57]:の最終行<br>
【誤】
```python
plt.ylabel("Recall") | 
```
【正】
```python
plt.ylabel("Recall")
plt.legend(loc="best")
```

| 場所        | 誤     | 正   |
| :---------- | :--------- | :-------- |
| p287、下から3行目 | 領域のなので | 領域なので|
| p287、脚注 | 大体 | だいたい|
| p289、4行目 | わすれない | 忘れない|
| p292、4か所 | 他クラス | 多クラス|
| p294、下から10行目 | 他クラス | 多クラス|
| p297、13行目 | `r2`（R<sup>2</sup>スコア）`mean_squared_error` | `r2`（R<sup>2</sup>スコア）、`mean_squared_error`|
| p298、脚注 | 『戦略的データサイエンス』 | 『戦略的データサイエンス入門』|
| p308、2行目| | 変換機 | 変換器|
| p318、9行目 | だれか | 誰か|
| p327、下から12行目 | しかけ | 仕掛け|
| p328、2行目 | 現われた | 現れた|
| p331、5行目 | L2正則化 | L2正規化|
| p331、脚注 | 自乗和 | 二乗和|
| p341、下から9行目 | `doc_spacy = en_nlp(document, entity=False, parse=False)` | `doc_spacy = en_nlp(document)`|
| p342、下から18行目| `cv = StratifiedShuffleSplit(n_iter=5, test_size=0.99,` | `cv = StratifiedShuffleSplit(n_splits=5, test_size=0.99,`|
p348、9-10行目<br>
【誤】
```python
# このトピックを最も重要としている5つの文書を表示
    # 最初の2文を表示
```
【正】
```python
# このトピックを最も重要としている5つの文書を表示
for i in music[:10]:
    # 最初の2文を表示
```

| 場所        | 誤     | 正   |
| :---------- | :--------- | :-------- |
| p353、7行目 | ためし | 試し|
| p357、下から12行目| 前書き | まえがき|
| p359、10行目| 大体 | だいたい|

