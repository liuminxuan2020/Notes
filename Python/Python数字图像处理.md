# Python + OpenCV

## 基础知识

1.OpenCV Python 加载图像的API

```python
src = cv.imread("./Img/LENA.BMP")
cv.namedWindow("main", cv.WINDOW_AUTOSIZE)
cv.imshow("main", src)
cv.waitKey()
cv.destroyAllWindows()
```

2.设计获取图像信息的函数

```python
def get_image_info(image):
    print(image.shape)
    print(image.size)
    print(image.dtype)
```

3.获取视频图像

```python
def get_video():
    capture = cv.VideoCapture(0)
    while True:
        ret, frame = capture.read()
        frame = cv.flip(frame, 1)
        cv.imshow("video", frame)
        c = cv.waitKey(50)
        if c == 30:
            break
```

 ## 色彩空间

### 1.什么是色彩空间？

#### 色彩模型

RGB HSV HIS YCrCb YUV

H:0 - 180

S: 0 - 255

V: 2 -255

#### OpenCV转换API

```python
def colorspace_change(image):
    gray = cv.cvtColor(image, cv.COLOR_BGR2GRAY)
    cv.imshow("gray", image)
    hsv = cv.cvtColor(image, cv.COLOR_BGR2HSV)
    cv.imshow("hsv", hsv)
    yuv = cv.cvtColor(image, cv.COLOR_BGR2YUV)
    cv.imshow("yuv", yuv)
    ycrcb = cv.cvtColor(image, cv.COLOR_BGR2YCrCb)
    cv.imshow("ycrcb", ycrcb)
```

#### 最常见的转换

HSV - RGB

YUV - RGB

### 2.inRange的使用

```python
def extrace_object(image):
    capture = cv.VideoCapture("")
    while True:
        ret, frame = capture.read()
        if not ret:
            break
        hsv = cv.cvtColor(frame, cv.COLOR_BGR2HSV)
        lower_hsv = np.array([37, 43, 46])
        upper_hsv = np.array([77, 255, 255])
        mask = cv.inRange(hsv, lowerb=lower_hsv, upperb=upper_hsv)
        cv.imshow("video", frame)
        cv.imshow("video", mask)
        c = cv.waitKey(40)
        if c == 27:
            break
```



### 3.通道的分离与合并

## 像素运算

### 算数运算

1.加 减 乘 除

2.可以用来调节亮度，调节对比度

3.获取均值

```
M1 = cv.mean(img1)  # 均值
```

4.获取均值和方差

```
m1, dev = cv.meanStdDev(img1)
```

### 逻辑运算

