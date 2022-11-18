---
layout: default
---
- [ボストン住宅価格データセットについて](#boston)
- [p.258のセル[21]について](#p258)
- [Spacyのモデルロードについて](#spacy)
- [3章のプロットで警告が出る](#plot)
- [get_feature_names`の変更について](#get_feature_names)
- [図3-13について](#nmf)
- [p.80 のPandas警告について](#pandas)

# ボストン住宅価格データセットについて <a name="boston"/>

`load_boston()`関数を実行すると下記のような警告が表示される。

```
FutureWarning: Function load_boston is deprecated; `load_boston` is deprecated in 1.0 and will be removed in 1.2.
```

この警告に書かれているように、ボストン住宅価格データセットには倫理上の問題が指摘されており、
データサイエンスや機械学習における倫理の学習、教育以外の目的で使用することは推奨されなくなっている。

Scikit-learn 1.2リリース後の対応としては、3つの方法が考えられる。
- 1.1を使いつづける
- ボストン住宅価格データセットを別の場所から入手する
- 代替データセットを用いる。

### 1.1 を使い続ける
```
pip install scikit-learn==1.1.X
```
のようにすれば、scikit-learnのバージョンを変更することができる。

### ボストン住宅価格データセットを別の場所から入手する
ボストン住宅価格データセットは`http://lib.stat.cmu.edu/datasets/boston`
から入手できる。下記の関数を用いれば、利用できるはずだ。

``` python
import pandas as pd
import numpy as np
from sklearn.utils import Bunch

def load_boston():
    data_url = "http://lib.stat.cmu.edu/datasets/boston"
    raw_df = pd.read_csv(data_url, sep="\s+", skiprows=22, header=None)
    data = np.hstack([raw_df.values[::2, :], raw_df.values[1::2, :2]])
    target = raw_df.values[1::2, 2]
    feature_names = ['CRIM', 'ZN', 'INDUS', 'CHAS', 'NOX', 'RM', 'AGE', 'DIS', 'RAD',
        'TAX', 'PTRATIO', 'B', 'LSTAT']
    return Bunch(data=data, target=target, feature_names=np.array(feature_names))
```

### 代替データセットを用いる

ボストン住宅価格データセットの代わりに、カリフォルニア住宅価格が提供されている。
`load_boston()`に変えて`fetch_california_housing()`を用いる。

``` python
from sklearn.datasets import fetch_california_housing
c = fetch_california_housing()
```

特徴量の名前や数も異なるので、全く同じように使用することはできないが、
ボストン住宅価格データセットに対して行ったことをカリフォルニア住宅価格データセットに対して
行うことは、良い演習課題となるだろう。

---

# p.258 セル[21]のコードが動作しない <a name="p258"/>

これはmglearnのバグで、データポイントとラベルの数が合致していないことが原因だ。
matplotlibの以前のバージョンではこの不一致を無視していたため顕在化しなかったのだが、
いつからか不一致をチェックするようになったためバグが顕在化した。
これに対応するためにはmglearnを修正する必要がある。
原著者がgithub上のコードを修正してくれない(2022年11月現在)ので、ソースを直接編集する。

`mglearn/plot_grid_search.py`の37行目近辺の

``` python
    plt.xticks(range(len(results)), [str(x).strip("{}").replace("'", "") for x
                                     in grid_search.cv_results_['params']],
               rotation=90)
```
このコードを下記のように改変する。

``` python
    plt.xticks(range(len(results)), [str(x).strip("{}").replace("'", "") for x
                                     in results['params']],                       
               rotation=90)
```


---

# 3章のプロットで警告が出る <a name="plot">
matplotlibのバージョンによっては、3章のプロットで`c`という名前のパラメータに関して警告が出る。
これは1文字のパラメータを避けるためで`color`に変更することが推奨されている。

気にならなければ放置しても問題ないが、8刷では`color`に変更済みである。

---

# Spacyのモデルロードについて <a name="spacy">

第7刷まではp.340 で下記のようにして英語モデルをロードしている。

``` python
# spacyの英語モデルをロード
en_nlp = spacy.load('en')
```

Spacyのバージョンアップによってこのコードは動作しなくなった。まず、下記のように、ターミナル上で明示的にモデルをダウンロードする必要がある。

``` 
> python -m spacy download en_core_web_sm
```

さらに、英語モデルの名前をより詳細に指定する。
``` python
# spacyの英語モデルをロード
en_nlp = spacy.load('en_core_web_sm')
```

---
# get_feature_namesの変更について <a name="get_feature_names"/>

scikit-learnの特徴量抽出クラスのインスタンスが持つ特徴量の名前を返すメソッドの
名前が`get_feature_names`から`get_feature_names_out`へ変更され、
`get_feature_names`はobsoleteとなっている。このためこのメソッドを実行するたびに
警告が出力される。
scikit-learn 1.1では問題なく動作するが、警告が煩わしい場合には`_out`を追加すればよい。

---
# 図3-13のNMF図について  <a name="nmf"/>

scikit-learnのパラメーア初期化方法が変更されたため、
NMFを実行した際に期待したものと異なる結果が得られる。

 <img alt="nmf.png" src="{{ site.baseurl }}/images/nmf.png" class="screenshot">

これを修正するには、`mglearn/plot_nmf.py`を編集する。`plot_nmf_illustration()`関数
内でNMFオブジェクトを作成する際に`init="random"`を追加すればよい。
16行目及び35行目をそれぞれ以下のように変更する

```python
#16行目
    nmf = NMF(random_state=0, init="random")

#35行目
    nmf = NMF(random_state=0, n_components=1, init="random")
```

---
# p.80 のPandas警告について <a name="pandas"/>

p.80 のコードを実行するとPandasが以下のような警告を出力する。
```
FutureWarning: Support for multi-dimensional indexing (e.g. `obj[:, None]`)
is deprecated and will be removed in a future version.
Convert to a numpy array before indexing instead.
```

これは下記のコード部分で発生している。

```
# 日付に基づいて価格を予測
X_train = data_train.date[:, np.newaxis]
```

このような多次元配列のようなアクセスの仕方を、今後のPandasでは禁止するため、事前に警告が
出ているだけで、現状では動作には問題ない。警告を消したければ、
以下のようにデータフレームをNumPy配列に変換してからアクセスするようにすればよい。

```
X_train = np.array(data_train.date)[:, np.newaxis]
```