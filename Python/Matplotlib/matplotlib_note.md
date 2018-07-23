# matplotlib

### 导入plt
* import matplotlib.pyplot as plt

### 折线图
* plt.plot(x, y, linestyle='-', color='red', marker='.')

### 显示图像
* plt.show()

### 绘制子图
* plt.subplot(221)   
(表示2行2列第1个图,在调用图形函数前调用)

### 生成图例
* plt.legend([list])

## 附表
### 23种点形状
|符号|形状|符号|形状|
|:-:|:-:|:-:|:-:|
|.|point|,|pixel|
|o|circle|v|triangle_down|
|^|triangle_up|<|triangle_left|
|>|triangle_right|1|tri_down|
|2|tri_up|3|tri_left|
|4|tri_right|8|octagon|
|s|square|p|pentagon|
|*|star|h|hexagon1|
|H|hexagon2|+|plus|
|x|x|D|diamond|
|d|thin_diamond||

### 8种內建默认颜色的缩写
|缩写|color|缩写|color|
|:-:|:-:|:-:|:-:|
|r|red|g|green|
|b|blue|c|cyan|
|y|yellow|m|magentay|
|k|black|w|white|

### 4种线性
|符号|线型|符号|线型|
|:-:|:-:|:-:|:-:|
|-|实线|--|虚线|
|-.|点划线|:|点线|