# adjustText

```python
mtcars = pd.read_csv('../tmp/mtcars.csv')
labels = mtcars['Unnamed: 0']
f = plt.figure()
r = f.canvas.get_renderer()
xs, ys = mtcars['wt'], mtcars['mpg']
paths = plt.scatter(xs, ys)
texts = []
for x, y, s in zip(xs, ys, labels):
    texts.append(plt.text(x, y, s, bbox={'pad':0.0, 'alpha':0}, size=7))

#plt.show()
```
![alt tag](https://raw.github.com/Phlya/adjustText/master/mtcars_before.png)
```python
adjust_text(xs, ys, texts, arrowprops=dict(arrowstyle='-', color='k'), bbox={'pad':0, 'alpha':0}, size=7)
plt.show()
```
![alt tag](https://raw.github.com/Phlya/adjustText/master/mtcars_after.png)

Unfortunately there is some randomness in the algorithm (I don't know where it comes from, except for a little randomness on the edges of the image), so the result is slightly different each time and is not necessarily equally good (but it's never bad, at least with this example!).
