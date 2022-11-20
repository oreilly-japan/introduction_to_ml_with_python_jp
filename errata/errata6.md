## �wPython�ł͂��߂�@�B�w�K�x��6������\

���L�̌�肪����܂����B���l�т��Ē����������܂��B

�{�y�[�W�Ɍf�ڂ���Ă��Ȃ���A�ȂǊԈႢ�����������́Ajapan��oreilly.co.jp�܂�
���m�点���������B

2019�N5���X�V


| �ꏊ        | ��     | ��   |
| :---------- | :--------- | :-------- |
| pviii�A2�s�� | IPython�m�[�g�u�b�N | Jupyter Notebook
| p10�AIn[6]:��1-2�s�� | `import pandas as pd`<br>`from IPython import display` | `import pandas as pd`|


p13�AOut[8]:�����ւ�<br>
�y��z
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
�y���z
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

| �ꏊ        | ��     | ��   |
| :---------- | :--------- | :-------- |
| p13�A�T�\����1�s�� | 0.18 | 0.20|
| p29�A5�s�� | ���Ȃ� | �t���Ȃ�
| p29�A�\2-1����1�s��| 45�� | 45��|
| p29�A������4�s�� | �l������ | �l���t����|
| p30�A2�s�� | 50�� | 50��|
| p31�A7�s�� | 45�� | 45��|
| p40�A1�s�� | �S�� | �܂�����|
| p54�A17�s�� | �x�� | �x����|
| p57�A2�s�� | �}�� | ����|
| p61�A�T�\���̍ŏI�s | �� | �c�o|
| p72�A������7�s�� | �s���Ă��邱�ƂȂ�B | �s���Ă��邱�ƂɂȂ�B|
| p73�A������10�s�� | �d�������� | �d����������|
| p86�A������10�s�� | ��Ȃ��� | �����|
| p105�A1�s�� | �}2-39 | �}2-45|
| p113�A�}2-54 | �d�ݍs��̗� | �d�ݍs��̗�|
| p129�A������8�s�� | ���ϒl�� | ���ϒl��|
| p147�A������8�s�� | ������ | �ς����|
| p153�A6�s�� | ���_�i0, 0) | ���_(0, 0)|
| p185�A������3�s�� | �戵 | ��舵��|
| p190�A12�s�� | �����̂�����̂ɂȂ��Ă��邩�́A | ���[�U�ɂƂ��ċ����[�����̂ɂȂ��Ă��邱�Ƃ��m�F����ɂ́A|
| p203�A12�s�� | �[�߂�� | ���߂��|
| p206�A�\4-1�̒��� | hours-per-week�Aoccupation�F�T������̘J������ | hours-per-week�F�T������̘J�����ԁAoccupation�F�E��|
| p208�AIn[1]:��1�s�� | `import pandas as pd` | `import pandas as pd`<br>`import os`|
| p208�A�\4-3�̒��� | hours-per-week�Aoccupation�F�T������̘J������ | hours-per-week�F�T������̘J�����ԁAoccupation�F�E��|

p223�A������1-2�s��<br>
�y��z
```python
X_train, X_test, y_train, y_test = train_test_split
    (boston.data, boston.target, random_state=0)
```
�y���z
```python
X_train, X_test, y_train, y_test = train_test_split(
    boston.data, boston.target, random_state=0)
```

p238�AIn[51]:<br>
�y��z
```python
# �^�[�Q�b�g�l�i�����^�����j�𒊏o
y = citibike.values
# ������"%s"��POSIX�����ɕϊ�
X = citibike.index.astype("int64").reshape(-1, 1) // 10**9
```
�y���z
```python
# �^�[�Q�b�g�l�i�����^�����j�𒊏o
y = citibike.values
# 10**9 �Ŋ�����POSIX�����ɕϊ�
X = citibike.index.astype("int64").to_numpy().reshape(-1, 1) // 10**9
```

p.239�A������2�s��<br>
�y��z
```python
X_hour = citibike.index.hour.reshape(-1, 1)
```
�y���z
```python
X_hour = citibike.index.hour.to_numpy().reshape(-1, 1)
```

p240�AIn[55]:��1-2�s��<br>
�y��z
```python
X_hour_week = np.hstack([citibike.index.dayofweek.reshape(-1, 1),
                         citibike.index.hour.reshape(-1, 1)])
```
�y���z
```python
X_hour_week = np.hstack([citibike.index.dayofweek.to_numpy().reshape(-1, 1),
                         citibike.index.hour.to_numpy().reshape(-1, 1)])
```

| �ꏊ        | ��     | ��   |
| :---------- | :--------- | :-------- |
| p248�A7�s�� | �͂����� | ������
| p254�AIn[16]: | `mglearn.plots.plot_label_kfold()` | `mglearn.plots.plot_group_kfold()`|
| p254�A�}5-4 | LabelKFold | GroupKFold|
| p268�A3�s�� | �葱 | �葱��|

p281�AIn[51]:��2-3�s��<br>
�y��z
```python
X, y = make_blobs(n_samples=(400, 50), centers=2, cluster_std=[7.0, 2],
                  random_state=22) 
```
�y���z
```python
X, y = make_blobs(n_samples=(400, 50), cluster_std=[7.0, 2], random_state=22)
```
| �ꏊ        | ��     | ��   |
| :---------- | :--------- | :-------- |
| p283�A������2�s�� | ���ׂĂ� | ���ׂĂ�|

p284�AIn[57]:��2-3�s��<br>
�y��z
```python
X, y = make_blobs(n_samples=(4000, 500), centers=2, cluster_std=[7.0, 2],
                  random_state=22) 
```
�y���z
```python
X, y = make_blobs(n_samples=(4000, 500), cluster_std=[7.0, 2], random_state=22)
```


p284�AIn[57]:�̍ŏI�s<br>
�y��z
```python
plt.ylabel("Recall") | 
```
�y���z
```python
plt.ylabel("Recall")
plt.legend(loc="best")
```

| �ꏊ        | ��     | ��   |
| :---------- | :--------- | :-------- |
| p287�A������3�s�� | �̈�̂Ȃ̂� | �̈�Ȃ̂�|
| p287�A�r�� | ��� | ��������|
| p289�A4�s�� | �킷��Ȃ� | �Y��Ȃ�|
| p292�A4���� | ���N���X | ���N���X|
| p294�A������10�s�� | ���N���X | ���N���X|
| p297�A13�s�� | `r2`�iR<sup>2</sup>�X�R�A�j`mean_squared_error` | `r2`�iR<sup>2</sup>�X�R�A�j�A`mean_squared_error`|
| p298�A�r�� | �w�헪�I�f�[�^�T�C�G���X�x | �w�헪�I�f�[�^�T�C�G���X����x|
| p308�A2�s��| | �ϊ��@ | �ϊ���|
| p318�A9�s�� | ���ꂩ | �N��|
| p327�A������12�s�� | ������ | �d�|��|
| p328�A2�s�� | ����ꂽ | ���ꂽ|
| p331�A5�s�� | L2������ | L2���K��|
| p331�A�r�� | ����a | ���a|
| p341�A������9�s�� | `doc_spacy = en_nlp(document, entity=False, parse=False)` | `doc_spacy = en_nlp(document)`|
| p342�A������18�s��| `cv = StratifiedShuffleSplit(n_iter=5, test_size=0.99,` | `cv = StratifiedShuffleSplit(n_splits=5, test_size=0.99,`|
p348�A9-10�s��<br>
�y��z
```python
# ���̃g�s�b�N���ł��d�v�Ƃ��Ă���5�̕�����\��
    # �ŏ���2����\��
```
�y���z
```python
# ���̃g�s�b�N���ł��d�v�Ƃ��Ă���5�̕�����\��
for i in music[:10]:
    # �ŏ���2����\��
```

| �ꏊ        | ��     | ��   |
| :---------- | :--------- | :-------- |
| p353�A7�s�� | ���߂� | ����|
| p357�A������12�s��| �O���� | �܂�����|
| p359�A10�s��| ��� | ��������|

