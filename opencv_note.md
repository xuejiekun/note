# OpenCV Note

## 基本操作
* 读取图像  
`cv2.imread`(filename, flags=None) -> M

| flags                | 功能  |
| :------------------- | :---- |
| cv2.IMREAD_COLOR     | 彩色  |
| cv2.IMREAD_GRAYSCALE | 灰度  |
| cv2.IMREAD_UNCHANGED | alpha |
<br/>

* 显示图像  
`cv2.imshow`(winname, mat)
* 输出图像  
`cv2.imwrite`(filename, img, params=None)
* 创建窗口  
`cv2.namedWindow`(winname, flags=None)

| flags               | 功能     |
| :------------------ | :------- |
| cv2.WINDOW_AUTOSIZE | 适应图像 |
| cv2.WINDOW_NORMAL   | 可以调节 |
<br/>

* 删除所有窗口  
`cv2.destroyAllWindows`()
* 删除指定窗口  
`cv2.destroyWindow`(winname)
* 延时响应  
`cv2.waitKey`(dealy=None) -> keynum

### sample
```py
import cv2

# 读取图像
img = cv2.imread('1.jpg', cv2.IMREAD_COLOR)

# 创建窗口并与图像绑定
cv2.namedWindow('image', cv2.WINDOW_NORMAL)
cv2.imshow('image', img)

# 'q'键退出并关闭窗口
while True:
    if cv2.waitKey(20) == ord('q'):
        break
cv2.destroyAllWindows()
```
***

## 视频
* 打开视频  
`cv2.VideoCapture`(vidname) -> VideoCapture
* 获取帧  
`cap.read`(image=None) -> flag, M
* 检测视频状态  
`cap.isOpened`() -> flag
* 获取视频参数  
`cap.get`(propId)
* 设置视频参数  
`cap.set`(propId, value)
* 释放视频  
`cap.release`()
<br/><br/>
* 设置编码  
`cv2.VideoWriter_fourcc`(c1 , c2, c3 , c4) -> codec
* 创建视频写出对象  
`cv2.VideoWriter`(vidname, codec, fps, (width,height)) -> VideoWriter
* 输出帧  
`out.write`(image)
***

## 绘图函数
| 参数      | 说明          |
| :-------- | :------------ |
| img       | 图像          |
| color     | 颜色          |
| thickness | 线宽,-1为填充 |
| lineType  | 线型          |
| shift     |               |

* 线  
`cv2.line`(img, pt1, pt2, color, thickness=None, lineType=None, shift=None)
* 圆  
`cv2.circle`(img, center, radius, color, thickness=None, lineType=None, shift=None)
* 矩形  
`cv2.rectangle`(img, pt1, pt2, color, thickness=None, lineType=None, shift=None)