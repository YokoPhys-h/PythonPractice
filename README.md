# 三項演算子でif文を短く書く
```python
age = 20
status = "成人" if age >= 18 else "未成年"
print(status)  # "成人"
```
つまり
```
真の場合の値 if 条件式 else 偽の場合の値
```

# DataFrame内の特定の値を変換する
trueを1、falseを0に変換する.

applyを使うなら以下.
```python
data=read.csv("hoge.csv")
data['column1']=data['column1'].apply(lambda x : 1 if x else 0)
```
replaceを使うなら以下.
```python
data['column1'].replace({True: 1, False: 0}, inplace=True)
```

型変換をする場合は以下
```python
data['column1']=data['column1'].astype(int)
```

# DataFrame内のデータをソートする. 
`acending=False`で降順になる.
`input=True`で元のDataFrameを変更する.
```python
data[['column1', 'sort_column']].sort_values('sort_column', ascending=False, inplace=True)
```

# indexを振り直す
`drop=True`で元のindexを削除する.
`inplace=True`で元のDataFrameを変更する.
```python
data.reset_index(drop=True, inplace=True)
```