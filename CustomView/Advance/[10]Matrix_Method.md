# Matrix方法


## 前言

在上一篇文章中，我们对Matrix做了一个简单的了解，偏向理论，在本文中则会详细的讲解Matrix的具体用法，以及Matrix的一些实用技巧。

<p id="method" />
## Matrix方法表

按照惯例，先放方法表做概览。

方法类别   | 相关API                                                 | 摘要
-----------|---------------------------------------------------------|------------------------
基本方法   | equals hashCode toString toShortString                  | 比较、 获取哈希值、 转换为字符串
数值操作   | set reset setValues getValues                           | 设置、 重置、 设置数值、 获取数值
数值计算   | mapPoints mapRadius mapRect mapVectors                  | 计算变换后的数值
设置(set)  | setConcat setRotate setScale setSkew setTranslate       | 设置变换
前乘(pre)  | preConcat preRotate preScale preSkew preTranslate       | 前乘变换
后乘(post) | postConcat postRotate postScale postSkew postTranslate  | 后乘变换
特殊方法   | setPolyToPoly setRectToRect rectStaysRect setSinCos     | 一些特殊操作
矩阵相关   | invert isAffine isIdentity                              | 求逆矩阵、 是否为仿射矩阵、 是否为单位矩阵 ...


## Matrix方法详解

### 构造方法

构造方法没有在上面表格中列出。

**无参构造**

```
Matrix ()
```
创建一个全新的Matrix，使用格式如下：

```
Matrix matrix = new Matrix();
```

通过这种方式创建出来的并不是一个数值全部为空的矩阵，而是一个单位矩阵,如下:

![](http://latex.codecogs.com/png.latex?
$$
\\left [ 
\\begin{matrix} 
1 & 0 & 0 \\\\
0 & 1 & 0 \\\\
0 & 0 & 1 
\\end{1} 
\\right ] 
$$)


**有参构造**

```
Matrix (Matrix src)
```

这种方法则需要一个已经存在的矩阵作为参数，如下:

```
Matrix matrix = new Matrix(src);
```

创建一个Matrix，并对src深拷贝(理解为新的matrix和src是两个对象，但内部数值相同即可)。


### 基本方法

基本方法内容比较简单，在此处简要介绍一下。

**1.equals**

比较两个Matrix的数值是否相同。

**2.hashCode**

获取Matrix的哈希值。

**3.toString**

将Matrix转换为字符串: `Matrix{[1.0, 0.0, 0.0][0.0, 1.0, 0.0][0.0, 0.0, 1.0]}`

**4.toShortString**

将Matrix转换为短字符串: `[1.0, 0.0, 0.0][0.0, 1.0, 0.0][0.0, 0.0, 1.0]`


### 数值操作

数值操作这一组方法可以帮助我们直接控制Matrix里面的数值。

**1.set**

```
void set (Matrix src)
```

没有返回值，有一个参数，作用是将参数Matrix的数值复制到当前Matrix中。如果参数为空，则重置当前Matrix，相当于`reset()`。

**2.reset**

```
void reset ()
```

重置当前Matrix(将当前Matrix重置为单位矩阵)。

**3.setValues**

```
void setValues (float[] values)
```

setValues的参数是浮点型的一维数组，长度需要大于9，拷贝数组中的前9位数值赋值给当前Matrix。

**4.getValues**

```
void getValues (float[] values)
```

很显然，getValues和setValues是一对方法，参数也是浮点型的一维数组，长度需要大于9，将Matrix中的数值拷贝进参数的前9位中。

### 数值计算

### set pre 与 post

### 特殊方法

### 矩阵相关

## Matrix实用技巧



