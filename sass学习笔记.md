##sass 学习笔记

*****
2016/7/31
*****
>今天刚刚接触sass，至于选择sass和less没有经验，总得先学一个，主要是听说less对条件选择和循环支持的不是太好。

###1 sass安装
由于sass的使用ruby开发，所以我们首先要安装ruby环境，至于ruby我也不是很了解。如果出现了这种错误
>Could not find a valid gem 'sass' (>= 0) in any repository

应该是没有添加ruby源，至于这是个什么东西也不清楚，按照下面的做
>$ gem sources --add http://rubygems.org/

当然你可以先用`gem sources`看一下查看是否有这个源。如果碰到如下问题

>ERROR:  While executing gem ... (Gem::OperationNotSupportedError)Not connected to a tty and no default specified

这是因为国内网络原因（你懂的），导致 rubygems.org 存放在 Amazon S3 上面的资源文件间歇性连接失败。而万能的淘宝也提供了一个类似的源
所以安装可以通过这个链接上面的来。[http://www.w3cplus.com/sassguide/install.html](http://www.w3cplus.com/sassguide/install.html)

当然上面的sass资料都是不错的，入门的话建议看看。

###2 为什么要用sass
关于这个问题可能我要在这里班门弄斧了，因为自己是刚刚入门。最直接的理由就是有时碰到一些问题，比如：
>css代码冗余多（可能是自己不熟悉css里面的DRY规则，因为css学的真心不好）

>尤其是开始的时候清除浮动，每个需要清除浮动的元素都会加上一段清除浮动的代码，后来学会了直接定义一个.clearfix。可是当我们要是想实现bootstrap的栅格系统的col-xs-3、col-xs-4等等其实我们希望能够传进一个参数就可以做出相应的修改，但是css没有参数变量这回事，那么sass可以办到
>有时候真希望能给它个变量，根据我的变量来展示不同的效果

这里有篇文章讲述了为什么要用预编译处理[https://segmentfault.com/q/1010000002527156/a-1020000002527759](https://segmentfault.com/q/1010000002527156/a-1020000002527759)

### 3 我的参考文章
由于个人英文不咋的，所以看得文章绝大多数还是中文，尤其是刚刚接触一个新东西时，肯定先看中文，觉得有些问题解决不了时，就会去看看官网。

[http://sass.bootcss.com/docs/sass-reference/](http://sass.bootcss.com/docs/sass-reference/)

[http://www.w3cplus.com/sassguide/index.html](http://www.w3cplus.com/sassguide/index.html)

[使用sass的8个意见](http://www.w3cplus.com/preprocessor/8-tips-help-get-best-sass.html)

[管理组织自己的sass项目结构](http://www.w3cplus.com/preprocessor/architecture-sass-project.html)

###4 工具使用
***
####sublime 使用环境
>添加插件sass和sass build;快捷键Ctrl+B

>然后就是sublime  markdown的一些开发插件 [http://www.jianshu.com/p/aa30cc25c91b](http://www.jianshu.com/p/aa30cc25c91b)
***
####在线sass编译

>[http://www.sassmeister.com/](http://www.sassmeister.com/)

###5 遇到问题
>Error: Invalid GBK character "\xE5"on line 4 of demo1.scss
  Use --trace for backtrace.

>解决办法： 
1.命令行工具同理 
找到ruby的安装目录，里面也有sass模块，如这个路径： 
C:/Ruby/lib/ruby/gems/1.9.1/gems/sass-3.3.14/lib/sass 
在这个文件里面engine.rb，添加一行代码Encoding.default_external = Encoding.find(‘utf-8’) 放在所有的require XXXX 之后即可。

这里是用命令行进行单个scss文件进行编译，绝大多数情况之下应该会用其他插件，比如sublime的scss插件，能够直接编译并且生成对应的css文件

###6 使用技巧和经验
>1 [sass的组织结构](http://www.w3cplus.com/preprocessor/architecture-sass-project.html)
******

>2 [合适运用minix和placeholder](http://www.w3cplus.com/preprocessor/sass-mixin-placeholder.html)

>3 学习使用基本的语法写几个实例（主要体会变量，minix和placeholder什么时候用），就可以学习使用csscore  compass这些sass库，当然有机会多看看里面的原代码

******

###7 练习实例
[http://www.w3cplus.com/preprocessor/centering-with-sass.html](http://www.w3cplus.com/preprocessor/centering-with-sass.html)

>####*最后个人觉得掌握石器时代的css是最重的*


