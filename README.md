# 1、迎合你的需求
当你需要一些`定制内容`的公章或私章图片，刚好你又懂点Java基础知识，那么你可以使用这个工具。

# 2、生成的效果图一览
## 2.1 公章效果图

------------


**圆形公章：**

![](http://p27z4ahy7.bkt.clouddn.com/2018/11/11/c27195ed6f54f757300270e800e51f76.png)    ![](http://p27z4ahy7.bkt.clouddn.com/2018/11/11/469aa4b13d7af3bbed4387d769a87b8f.png)

![](http://p27z4ahy7.bkt.clouddn.com/2018/11/11/7c997e4ebbcb55f93aa83bd79085879c.png)    ![](http://p27z4ahy7.bkt.clouddn.com/2018/11/11/274b7f578c31c616480586a50cb65f3f.png)



**椭圆公章：**

![](http://p27z4ahy7.bkt.clouddn.com/2018/11/11/94b034a772aacf887bfb20f276185760.png)    ![](http://p27z4ahy7.bkt.clouddn.com/2018/11/11/72b350a0844e43b2e6e213bbdbdf793f.png)

![](http://p27z4ahy7.bkt.clouddn.com/2018/11/11/932175483d6a7fd0dc45a6cf838bb59e.png)

## 2.2 私章效果图

------------


![](http://p27z4ahy7.bkt.clouddn.com/2018/11/11/4ff5688d9095fac9e0246c761c5e023b.png)    ![](http://p27z4ahy7.bkt.clouddn.com/2018/11/11/6b7bd6b5dd572073a04f84df3dec47f6.png)

![](http://p27z4ahy7.bkt.clouddn.com/2018/11/11/2bb40f0497be2bc5d665c970691bc305.png)    ![](http://p27z4ahy7.bkt.clouddn.com/2018/11/11/67d501a8c2c1756271b019eb8441a10f.png)

![](http://p27z4ahy7.bkt.clouddn.com/2018/11/11/ab9afcc736b7d22dac635e5ce2f59d3b.png)

# 3.使用方法
```java
import cn.localhost01.seal.SealUtil;
import cn.localhost01.seal.configuration.SealCircle;
import cn.localhost01.seal.configuration.SealConfiguration;
import cn.localhost01.seal.configuration.SealFont;

import java.awt.*;
import java.io.IOException;

public class Main {

    public static void main(String[] args) throws Exception {
        /**
         * 印章配置文件
         */
        SealConfiguration configuration = new SealConfiguration();

        /**
         * 主文字
         */
        SealFont mainFont = new SealFont();
        mainFont.setBold(true);
        mainFont.setFontFamily("楷体");
        mainFont.setMarginSize(10);
        /**************************************************/
        //mainFont.setFontText("欢乐无敌制图网淘宝店专用章");
        //mainFont.setFontSize(35);
        //mainFont.setFontSpace(35.0);
        /**************************************************/
        //mainFont.setFontText("ZHITUWANG CO.LTDECIDDO SH  NANNINGSHI");
        //mainFont.setFontSize(20);
        //mainFont.setFontSpace(15.0);
        /**************************************************/
        mainFont.setFontText("欢乐无敌制图网淘宝店专用章");
        mainFont.setFontSize(25);
        mainFont.setFontSpace(12.0);

        /**
         * 副文字
         */
        SealFont viceFont = new SealFont();
        viceFont.setBold(true);
        viceFont.setFontFamily("宋体");
        viceFont.setMarginSize(5);
        /**************************************************/
        //viceFont.setFontText("123456789012345");
        //viceFont.setFontSize(13);
        //viceFont.setFontSpace(12.0);
        /**************************************************/
        viceFont.setFontText("正版认证");
        viceFont.setFontSize(22);
        viceFont.setFontSpace(12.0);

        /**
         * 中心文字
         */
        SealFont centerFont = new SealFont();
        centerFont.setBold(true);
        centerFont.setFontFamily("宋体");
        /**************************************************/
        //centerFont.setFontText("★");
        //centerFont.setFontSize(100);
        /**************************************************/
        //centerFont.setFontText("淘宝欢乐\n制图网淘宝\n专用章");
        //centerFont.setFontSize(20);
        /**************************************************/
        //centerFont.setFontText("123456789012345");
        //centerFont.setFontSize(20);
        /**************************************************/
        centerFont.setFontText("发货专用");
        centerFont.setFontSize(25);

        /**
         * 抬头文字
         */
        SealFont titleFont = new SealFont();
        titleFont.setBold(true);
        titleFont.setFontFamily("宋体");
        titleFont.setFontSize(22);
        /**************************************************/
        //titleFont.setFontText("发货专用");
        //titleFont.setMarginSize(68);
        //titleFont.setFontSpace(10.0);
        /**************************************************/
        titleFont.setFontText("正版认证");
        titleFont.setMarginSize(68);
        titleFont.setMarginSize(27);

        /**
         * 添加主文字
         */
        configuration.setMainFont(mainFont);
        /**
         * 添加副文字
         */
        configuration.setViceFont(viceFont);
        /**
         * 添加中心文字
         */
        configuration.setCenterFont(centerFont);
        /**
         * 添加抬头文字
         */
        //configuration.setTitleFont(titleFont);

        /**
         * 图片大小
         */
        configuration.setImageSize(300);
        /**
         * 背景颜色
         */
        configuration.setBackgroudColor(Color.RED);
        /**
         * 边线粗细、半径
         */
        //configuration.setBorderCircle(new SealCircle(3, 140, 140));
        configuration.setBorderCircle(new SealCircle(3, 140, 100));
        /**
         * 内边线粗细、半径
         */
        //configuration.setBorderInnerCircle(new SealCircle(1, 135, 135));
        configuration.setBorderInnerCircle(new SealCircle(1, 135, 95));
        /**
         * 内环线粗细、半径
         */
        //configuration.setInnerCircle(new SealCircle(2, 105, 105));
        configuration.setInnerCircle(new SealCircle(2, 85, 45));

        //1.生成公章
        try {
            SealUtil.buildAndStoreSeal(configuration, "C:\\Users\\localhost01\\Desktop\\公章.png");
        } catch (IOException e) {
            e.printStackTrace();
        }

        //2.生成私章
        SealFont font = new SealFont();
        font.setFontSize(120).setBold(true).setFontText("诸葛孔明");
        SealUtil.buildAndStorePersonSeal(300, 16, font, "印", "C:\\Users\\localhost01\\Desktop\\私章.png");
    }

}
```

通过`SealUtil\src\Main.java`文件来进行配置各种参数，不断调整，达到你需要的效果！

# 4、开发背景
本身这个小工具是我接的一个外包活儿，但是最后价格没谈拢，我就没卖了。

最后吐槽一下那个需求方，接下活儿时，报价是1K，做好人家却反悔只出300。

好吧，高雅的程序员**就算是免费开源，也不会低价贱卖！** o(∩_∩)o 哈哈
