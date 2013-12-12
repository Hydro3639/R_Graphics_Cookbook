# Legend guide:ggplot2ͼ��ʹ�÷�������

��������Ϊ�������£����������
http://docs.ggplot2.org/current/guide_legend.html

## �÷�������Usage
```
guide_legend(title = waiver(), title.position = NULL, title.theme = NULL, title.hjust = NULL, 
  title.vjust = NULL, label = TRUE, label.position = NULL, label.theme = NULL, 
      label.hjust = NULL, label.vjust = NULL, keywidth = NULL, keyheight = NULL, direction = NULL, 
      default.unit = "line", override.aes = list(), nrow = NULL, ncol = NULL, byrow = FALSE, 
      reverse = FALSE, order = 0, ...)
```
## ������⣺Arguments
### ͼ����ʾ���
�����ǿ����Ƿ���ʾͼ����ѡ�
������ǲ���Ҫ����ͼ��,����ֻ��Ҫ���ã�colour=FALSE

```r
library(ggplot2)
first = ggplot(mpg, aes(displ, hwy, colour = cyl)) + geom_point()
first
first + guides(colour = FALSE)
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-11.png) ![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-12.png) 

ע�����������õ���colour�����ɵ�ͼ��,�����������ǿ���ͼ����ʱ����colour

### title:����
#### ���ñ����Ƿ���ʾ��title=NULL

```r
first + guides(colour = guide_legend(title = NULL))
second = ggplot(mpg, aes(displ, hwy, colour = factor(cyl))) + geom_point()
second
second + guides(colour = guide_legend(title = NULL))
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-21.png) ![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-22.png) ![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-23.png) 


#### ��Ҫ֪����
���������fill�������ɫ,��ô����ȥ��ͼ������Ҫ��fill, ȥ������,Ҳ��fill,���£�

```r
third = ggplot(mpg, aes(cyl, hwy, fill = factor(cyl))) + geom_boxplot()
third
third + guides(fill = FALSE)
third + guides(fill = guide_legend(title = NULL))
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-31.png) ![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-32.png) ![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-33.png) 

#### ����title�ı����

```r
third + guides(fill = guide_legend(title = "how"))
```

![plot of chunk unnamed-chunk-4](figure/unnamed-chunk-4.png) 

### title.position:����λ��
����λ�÷�Ϊ���֣�top(),bottom(��),left(��),right(��)

```r
third + guides(fill = guide_legend(title.position = "top"))
third + guides(fill = guide_legend(title.position = "bottom"))
third + guides(fill = guide_legend(title.position = "left"))
third + guides(fill = guide_legend(title.position = "right"))
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-51.png) ![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-52.png) ![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-53.png) ![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-54.png) 

#### title.theme:������ʽ����
�����ѡ�������ǿ�������Ŀ��Ʊ����size(��С),face(����),colour(��ɫ),angel(��ת�Ƕ�).

```r
third + guides(fill = guide_legend(title.theme = element_text(size = 15, face = "italic", 
    colour = "red", angle = 30)))
```

![plot of chunk unnamed-chunk-6](figure/unnamed-chunk-6.png) 

#### title.hjust:ˮƽ������ڶ��뷽ʽ
����Ķ��뷽ʽ��Ϊ���������ʾ��������Ҫ���������һ������.

```r
third + guides(fill = guide_legend(title.hjust = 0, nrow = 1))
third + guides(fill = guide_legend(title.hjust = 0.5, nrow = 1))
third + guides(fill = guide_legend(title.hjust = 1, nrow = 1))
```

![plot of chunk unnamed-chunk-7](figure/unnamed-chunk-71.png) ![plot of chunk unnamed-chunk-7](figure/unnamed-chunk-72.png) ![plot of chunk unnamed-chunk-7](figure/unnamed-chunk-73.png) 

#### title.vjust:��ֱ������ڶ��뷽ʽ

```r
third + guides(fill = guide_legend(title.vjust = 0, title.position = "left"))
third + guides(fill = guide_legend(title.vjust = 0.5, title.position = "left"))
third + guides(fill = guide_legend(title.vjust = 1, title.position = "left"))
```

![plot of chunk unnamed-chunk-8](figure/unnamed-chunk-81.png) ![plot of chunk unnamed-chunk-8](figure/unnamed-chunk-82.png) ![plot of chunk unnamed-chunk-8](figure/unnamed-chunk-83.png) 


### label:��ǩ
#### �Ƿ�����????
logical. If TRUE then the labels are drawn. If FALSE then the labels are invisible.
����ѡ�ߣ�TRUE��FALSE�����Ƿ����ɱ�ǩ

```r
third + guides(fill = guide_legend(label = TRUE))
third + guides(fill = guide_legend(label = FALSE))
```

```
## Error: grob 'NULL' not found
```

![plot of chunk unnamed-chunk-9](figure/unnamed-chunk-9.png) 

#### label.position
�ͱ���λ������

```r
third + guides(fill = guide_legend(label.position = "top"))
third + guides(fill = guide_legend(label.position = "bottom"))
third + guides(fill = guide_legend(label.position = "left"))
third + guides(fill = guide_legend(label.position = "right"))
```

![plot of chunk unnamed-chunk-10](figure/unnamed-chunk-101.png) ![plot of chunk unnamed-chunk-10](figure/unnamed-chunk-102.png) ![plot of chunk unnamed-chunk-10](figure/unnamed-chunk-103.png) ![plot of chunk unnamed-chunk-10](figure/unnamed-chunk-104.png) 


#### label.theme����ǩ����ʽ
�ͱ������ʽһ����

```r
third + guides(fill = guide_legend(label.theme = element_text(size = 15, face = "italic", 
    colour = "red", angle = 30)))
```

![plot of chunk unnamed-chunk-11](figure/unnamed-chunk-11.png) 

#### label.hjust:ˮƽ���뷽ʽ

```r
third + guides(fill = guide_legend(label.hjust = 0, label.position = "top"))
third + guides(fill = guide_legend(label.hjust = 0.5, label.position = "top"))
third + guides(fill = guide_legend(label.hjust = 1, label.position = "top"))
```

![plot of chunk unnamed-chunk-12](figure/unnamed-chunk-121.png) ![plot of chunk unnamed-chunk-12](figure/unnamed-chunk-122.png) ![plot of chunk unnamed-chunk-12](figure/unnamed-chunk-123.png) 

#### label.vjust:��ֱ������뷽ʽ

```r
third + guides(fill = guide_legend(label.vjust = 0, label.position = "left"))
third + guides(fill = guide_legend(label.vjust = 0.5, label.position = "left"))
third + guides(fill = guide_legend(label.vjust = 1, label.position = "left"))
```

![plot of chunk unnamed-chunk-13](figure/unnamed-chunk-131.png) ![plot of chunk unnamed-chunk-13](figure/unnamed-chunk-132.png) ![plot of chunk unnamed-chunk-13](figure/unnamed-chunk-133.png) 

### keywidth��ͼ���,keyheightͼ���

```r
third + guides(fill = guide_legend(keywidth = 5))
third + guides(fill = guide_legend(keywidth = 10))
third + guides(fill = guide_legend(keyheight = 1))
third + guides(fill = guide_legend(keyheight = 5))
```

![plot of chunk unnamed-chunk-14](figure/unnamed-chunk-141.png) ![plot of chunk unnamed-chunk-14](figure/unnamed-chunk-142.png) ![plot of chunk unnamed-chunk-14](figure/unnamed-chunk-143.png) ![plot of chunk unnamed-chunk-14](figure/unnamed-chunk-144.png) 


#### direction
A character string indicating the direction of the guide. One of "horizontal" or "vertical."

```r
third + guides(fill = guide_legend(direction = "horizontal"))
third + guides(fill = guide_legend(direction = "vertical"))
```

![plot of chunk unnamed-chunk-15](figure/unnamed-chunk-151.png) ![plot of chunk unnamed-chunk-15](figure/unnamed-chunk-152.png) 


#### default.unit
A character string indicating unit for keywidth and keyheight.
#### override.aes
��������趨��͸���Ⱥܵͣ�ͬ�����ǵ�ͼ���е�ɫ��Ҳ��ܵ���
���override.aes���ǿ���ͼ������ɫ���䡣

```r
four = ggplot(mpg, aes(displ, hwy, colour = factor(cyl))) + geom_point(alpha = 1/10)
four + guides(colour = guide_legend(override.aes = list(alpha = 1)))
```

![plot of chunk unnamed-chunk-16](figure/unnamed-chunk-16.png) 

#### nrow������û�еĸ���

```r
third
third + guides(fill = guide_legend(nrow = 4))
third + guides(fill = guide_legend(nrow = 3))
third + guides(fill = guide_legend(nrow = 2))
```

![plot of chunk unnamed-chunk-17](figure/unnamed-chunk-171.png) ![plot of chunk unnamed-chunk-17](figure/unnamed-chunk-172.png) ![plot of chunk unnamed-chunk-17](figure/unnamed-chunk-173.png) ![plot of chunk unnamed-chunk-17](figure/unnamed-chunk-174.png) 

#### ncol:����ÿ�еĸ���

```r
third
third + guides(fill = guide_legend(ncol = 4))
third + guides(fill = guide_legend(ncol = 2))
third + guides(fill = guide_legend(ncol = 1))
```

![plot of chunk unnamed-chunk-18](figure/unnamed-chunk-181.png) ![plot of chunk unnamed-chunk-18](figure/unnamed-chunk-182.png) ![plot of chunk unnamed-chunk-18](figure/unnamed-chunk-183.png) ![plot of chunk unnamed-chunk-18](figure/unnamed-chunk-184.png) 

#### byrow:�ᣬbycol����
ͼ�������˳��

```r
third
third + guides(fill = guide_legend(ncol = 3, byrow = TRUE))
third + guides(fill = guide_legend(ncol = 3, bycol = TRUE))
```

![plot of chunk unnamed-chunk-19](figure/unnamed-chunk-191.png) ![plot of chunk unnamed-chunk-19](figure/unnamed-chunk-192.png) ![plot of chunk unnamed-chunk-19](figure/unnamed-chunk-193.png) 

#### reverse
������ʾͼ��

```r
third
third + guides(fill = guide_legend(reverse = TRUE))
```

![plot of chunk unnamed-chunk-20](figure/unnamed-chunk-201.png) ![plot of chunk unnamed-chunk-20](figure/unnamed-chunk-202.png) 

#### order
positive integer less that 99 that specify the order of this guide in the multiple guides. If 0 (default), the order is determined by a secret algorithm.
���������ġ�

```r
third
third + guides(fill = guide_legend(order = 5))
third + guides(fill = guide_legend(order = 0))
```

![plot of chunk unnamed-chunk-21](figure/unnamed-chunk-211.png) ![plot of chunk unnamed-chunk-21](figure/unnamed-chunk-212.png) ![plot of chunk unnamed-chunk-21](figure/unnamed-chunk-213.png) 

