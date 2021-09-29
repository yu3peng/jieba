https://www.katacoda.com/courses/ubuntu/playground

pip install jieba

wget https://raw.githubusercontent.com/fuqiuai/wordCloud/master/doc/%E5%8D%81%E4%B9%9D%E5%A4%A7%E6%8A%A5%E5%91%8A%E5%85%A8%E6%96%87.txt

mv %E5%8D%81%E4%B9%9D%E5%A4%A7%E6%8A%A5%E5%91%8A%E5%85%A8%E6%96%87.txt 19.txt

vi 19Read.py

```python
import jieba
txt = open("19.txt","r",encoding="utf-8").read()
words = jieba.lcut(txt)
counts = {}
for word in words:
    if len(word)==1:
        continue
    else:
        counts[word] = counts.get(word,0)+1
items = list(counts.items())
items.sort(key=lambda x:x[1],reverse=True)
for i in range(115):
    word,count = items[i]
    print("{0:<10}{1:>5}".format(word,count))
```

python3 19Read.py
