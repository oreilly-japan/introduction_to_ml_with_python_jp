---
---
# Pythonではじめる機械学習 サポートページ

## ボストン住宅価格データセットについて

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

```
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

```
from sklearn.datasets import fetch_california_housing
c = fetch_california_housing()
```

特徴量の名前や数も異なるので、全く同じように使用することはできないが、
ボストン住宅価格データセットに対して行ったことをカリフォルニア住宅価格データセットに対して
行うことは、良い演習課題となるだろう。






