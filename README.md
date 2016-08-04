# XDAttributedTool
给字符串设置富文本模式

提供了三个类方法，一行代码设置一段文字的不同颜色和字体。

针对需求：

1. 给不定长字符串设置一种字体和颜色
2. 给不定长字符串设置两段字体和颜色，只知某一段字符长度
3. 给不定长字符串设置三段字体和颜色，只知其中两段字符长度
4. 给定长字符串设置多段字体和颜色，知道每段字符长度

```Objective-C
/**
 *  给指定的NSString设置颜色和字体，不指定字符数
 *
 *  @param text  指定的字符串
 *  @param array @[颜色, 字体]
 *
 *  @return 富文本
 */
+ (NSMutableAttributedString *)setupOneAttributedText:(NSString *)text array:(NSArray *)array;

/**
 *  指定NSString设置颜色和字体，只支持两段式，三段式，指定部分字符数
 *
 *  @param text        指定的字符串
 *  @param startArray  @[字符数, 颜色, 字体]
 *  @param centreArray @[字符数, 颜色, 字体] 如果设置两段式此参数赋值 nil
 *  @param endArray    @[字符数, 颜色, 字体]
 *  @param 字符数       数组参数中的字符串元素，两段式时有且只有一个为有效值，另一个为@"0", 三段式时有且必须有两个为有效值，剩余一个为@"0"。为@"0"的元素数为不确定，计算得出。
 *
 *  @return 富文本
 */
+ (NSMutableAttributedString *)setupTrendsAttributedText:(NSString *)text startArray:(NSArray *)startArray centreArray:(NSArray *)centreArray endArray:(NSArray *)endArray;

/**
 *  指定NSString设置颜色和字体，只支持多段，指定所有字符数
 *
 *  @param text     指定的字符串
 *  @param firstObj @[字符数, 颜色, 字体], @[字符数, 颜色, 字体], ..., nil
 *
 *  @return 富文本
 */
+ (NSMutableAttributedString *)setupMoreAttributedText:(NSString *)text arrays:(id)firstObj, ... NS_REQUIRES_NIL_TERMINATION;
```

实现结果

![image](http://oalg33nuc.bkt.clouddn.com/image/Simulator%20Screen%20Shot%202016%E5%B9%B48%E6%9C%884%E6%97%A5%20%E4%B8%8B%E5%8D%886.40.48.png)