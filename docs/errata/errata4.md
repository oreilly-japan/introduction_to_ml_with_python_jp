---
layout: default
---
## 『Pythonではじめる機械学習』第4刷正誤表

下記の誤りがありました。お詫びして訂正いたします。

本ページに掲載されていない誤植など間違いを見つけた方は、japan＠oreilly.co.jpまで
お知らせください。




| 場所        | 誤     | 正   |
| :---------- | :--------- | :-------- |
| pv、下から3行目 | http://statweb.stanford.edu/~tibs/ElemStatLearn/ | http://web.stanford.edu/~hastie/ElemStatLearn/ |
| p69、下から11行目 | 追加されたされたかの | 追加されたの|
| p71、上から4行目 | 75データポイント | 50データポイント|
| p71、図2-23| | 凡例を追加<br>● Class 1　クラス0<br>▲ Class 0　クラス1|
| p71、下から5行目 | 75点とクラス1に属する75点を示す。 | 50点とクラス1に属する50点を示す。|
| p297、上から1-3行目（マイナス2行） | `print("Test set AUC: {:.3f}".format(`<br>`roc_auc_score(y_test, grid.decision_function(X_test))))`<br>`print("Test set accuracy: {:.3f}".format(grid.score(X_test, y_test)))`| `print("Test set AUC: {:.3f}".format(grid.score(X_test, y_test)))`|
| p297、上から9行目| Test set accuracy: 1.000 テストセットの精度 | （※この行を削除）|
| p366、「T」項目の上|statsmodelパッケージ 358|statsmodelパッケージ 358<br>SVM（サポートベクタマシン） 57, 90, 95-102, 254-255|


