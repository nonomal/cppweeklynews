
# C++ 中文周刊 常见问题 解答


[周刊项目地址](https://github.com/wanghenshui/cppweeklynews)

公众号

<img src="https://wanghenshui.github.io/cppweeklynews/assets/code.png" alt=""  width="30%">


qq群 [点击进入](https://qm.qq.com/q/6NGizNPyG4) 满了加这个 729240657

[RSS](https://github.com/wanghenshui/cppweeklynews/releases.atom)

经常在群里交流，发现有很多共性的问题，以及迷茫的点，大家重复交流很无聊，需要一些共识，这也是群聊的目的

大部分c++群聊聊天的内容都会包括本帖中讨论的各种争执，反复讨论很无聊，以后有重复的讨论就会把这个链接丢出来

之前通过发问卷收集了一些反馈 问卷地址 https://docs.qq.com/sheet/DYkllcE9scmtUUWlu?tab=ss_epaxm9&viewId=fv1&u=556ff788fee74403a1ab2ecd9e607b89

本文长期更新，按照更新顺序排列，目前更新时间为 2024-10-28

本文感谢赞助的朋友

- 啃萝卜
- 夏虫
- 祥子
- 天失败

---


## c++就业前景/什么时候能找到好工作/当前c++能做的业务场景

这个我做了一个表格，https://docs.qq.com/sheet/DYm1nV1ZUdGVNWnNh?tab=BB08J2

大家感兴趣也可以补充，我把表格内容列出来

- 1 ai搜广推 需要考虑35岁之后的职业焦虑，不过刚开始干肯定前途光明。这是离钱最近的地方
- 2 游戏/ 赚钱最多最广的方向，前提是游戏能成
- 2.5 hft 高频交易 赚钱，但门槛比较高圈子封闭爱装逼
- 2.6 其他和钱相关的项目(网关/web3) web3有被坑风险 
- 3 算法 (包括ai gpu/自动驾驶/机器人) 越老越吃香，前期薪资也高，但门槛高得离谱
- 3.9 机架 平台哥(网关网平rpc框架管理) 需要基础非常好，且岗位少
- 3.99 机架 编译器 llvm/ncc 岗位少 知识需要自己琢磨
- 4 机架(系统/数据库/nosql/对象存储文件系统) 曾经风口，人太多，有点卷
- 4.9 传统业务 curd 哥 份额基本被go吃掉
- 5 嵌入式 手机相关 相机算法/手机存储/手机基带/手机射频 手机赚钱，但现在手机没那么赚钱了
- 5.5 图像算法/音视频 越老越吃香，但怕你坚持不住
- 5.6 传统业务(通信/核心网/商用软件) 和上面有重叠项目  
- 5.7 传统软件上位机 qt 薪资可能不高，需要现场办公
- 6 嵌入式  汽车方向/无人机/物联网方向 汽车赚钱，处于风口
- 6.1 嵌入式 通信方向 传统行业不会失业。
- 6.2 嵌入式 普通单片机，苦逼现场哥

排名主要取决于成就感/薪资/发展 但实际上c++工作都很苦逼

对于应届生来说，主要是活下去，不一定强求非得干这个

已经入行的，大多有互相转的趋势，比如做基础架构的平台哥去做AI infra

或者做游戏的受不了了出来干平台

但做嵌入式肯定是苦的，如果你已经苦了，切换岗位代价高，那就去苦且有钱的地方，比如车行业


## 我该用哪个序列化库/哪个序列化库好？

选取库主要是取决于需求，要根据已有的场景做抉择，比如已经沾上grpc的屎， protobuf就躲不开

既然用protobuf，想换grpc也就只能去brpc

目前通用型屎protobuf较多的，甚至有基于protobuf的存储/算子引擎（扣字段）/内存分配器

通用性第二就是thrift

其次是flatbuffer 性能较好

c++如果不涉及跨语言边界，内部可以搞二进制自解析，比如struct_pack cista 还有redpanda/seastar都实现了自己的序列化

这些原理都是magic_ger（boost.pfr）就不展开了

一定还是要围绕需求的。前期开发可以用pb，后面慢慢切接口

## 现在学c++还有前途吗

学c++可以说是自找苦吃，计算机行业基本都需要终身学习

但c++不仅要终身学习，终身学习的途中你还会发现自己知道的越来越少

从沉没成本角度分析，前途不好，投入大于收益

但我觉的爱学的肯定你想换成别的语言也简单。毕竟你连c++都能忍

从已有的存量代码角度分析，c++肯定能活很久，所有语言所有范式，你翻一番就能在c++代码屎山里找到，吃屎饿不死

但受不了的人可能就用别的语言写一坨新的屎了

并且在cpu无明显进化的场景下，比如这几年intel磨洋工，这种场景下c++程序员是比较值钱的

从资方角度考虑，省CPU还是省人力，当人力不值钱，c++就不火

雇佣c++程序员如果能扣出来机器的钱，那就不愁找工作。目前来看还有一段距离

## cpp当前主要能做的业务，以及在某些业务中的竞争对手语言

业务上面说了 主要竞争对手其实是后端语言都竞争

和go 抢普通业务CURD开发，基本被抢光了

和java抢大数据infra开发， java基本抢光。c++活在底层组件里

和rust抢底层infra组件，rust靠一手安全抢了一些业务，这种主要看公司老板推动，不推就是c++的天下

和python抢算法，现在作为python后端活着

## 协程哪个好，无栈协程好还是有栈协程好

其实这个问题也是需求问题，我们讨论协程通常是忽略了调度器分配器的，这里正交一下场景非常多

当前无栈协程不算稳定，可以先有有栈协程，观望先

目前已有的结论是无栈协程IO处理更好，有栈协程计算更稳，但这只是通用结论，具体场景还得自己来测


## 除标准库外，常用的一些三方库（网络，序列化，ui...）总结

这种其实github搜关键字就好了

网络 asio/libuv/libevent/brpc等等

序列化 protobuf/thrift/flatbuffers/ 自定义序列化

ui qt ？不太了解

json github搜星最多的那个，如果不是性能要求，不要用rapid-json，他既不rapid，也不好用，接口难用的一

性能考虑可以simdjson yyjson glaze 字节那个soniccpp也行

这个后面慢慢补充吧 标记个TODO

## 有什么主要讲cpp工程而不是语法的书籍

工程只能从项目里找，一般可能就看看cppcon演讲了

或者最近有一本大规模c++程序设计可以看一下。我也下单了，有空写book review

这里也标记一个TODO

## 做算法C++要掌握到什么程度

能看懂基础语法，能把算法翻译成c++就行

我们把c++分成两类语法，业务级别/库级别

你需要掌握的就是业务级别，库级别特性比如enableif之类的你完全可以不看

重点在算法相关，比如浮点数可能有问题，标准库处理了太多异常你算法可以不考虑，可以优化

当然如果你做算法的库，可能还是得懂一点库级别特性

## 模板要学到什么程度

这个和上一个差不多，主要是模版有很多是库级别特性，但开发库的人千里挑一，业务哥用就完了

看你对自己的定位，你是平台哥要开发脚手架给别人用，你就得研究透模版偏特化/萃取之类的手段，给业务哥用


## 设计模式怎么学？我自己是做客户端，UI也好，业务逻辑也好，框架也好，自己写出来的总差点意思。没章法，不好维护

这种就是代码写得少抄的少了，你的场景什么应用也会有？github找到该项目，直接抄他的组织模式


## 指针和数组有什么区别？

这个是经典吵架问题，有啥区别，完全不一样，数组名能退化(decay)成指针，就这一个关联

## array和数组谁性能好/vector和我自己写的动态数组谁快

这种模糊问题不好回答，比较什么接口？比如array的[]和vector::emplace_back比，前者可能存在向量化

自己约束场景做压测最好，问是问不出来的

## c++多个版本，从哪个版本学习更容易开始工作

c++17 编译器是什么版本你就学什么版本，编译器目前默认17

## 为什么库都很难装，很难用。一个库一堆重复的宏

c++ 没有包管理器的问题

如果你是cmake，用cpm, 如果没有选择，可以尝试xmake，公司一般来说会用bazel/blade 后面三个原理类似

## 什么是右值，右值引用变量为什么不是右值/类型和值类别/右值引用 所有权

你要理解纯值类型 pure value，其他名次基本上就是为了延长生命周期做的代价

这个新人可以跳过。这一般不是重点

## 模板递归怎么写/concept怎么写/iterator怎么写

没有需求没法教会你，模版递归很容易栈溢出

concept你可以照着抄std::same_as

iterator可以随便抄一个容器的，重点是tag dispatch

## c++11的移动是个什么东西

移动语义可以写一本书，打个比方value左值是一个盒子，我可以通过move告诉编译器把盒子里的东西搬走

有时间的话可以看一下这篇：[C++的右值引用、移动和值类别系统，你所需要的一切](https://zclll.com/index.php/cpp/value_category.html)

## 各种编译失败/库的链接问题（为什么链接失败

这种只能搜索引擎搜，我也总结了个常见报错整理 https://wanghenshui.github.io/2019/11/01/compile.html

没有好的解决办法


## 有无对标python ply yacc的现代化的语法解析器？

boost::spirit 这个是最经典的也是比较难懂的，foothan他有个lexy

这种需求说实话有点小众

## 单独的一条if或者while语句要不要加花括号/左花括号{要不要换行

格式问题一律clang-format修复，自己的规则自己维护，因为格式吵架过于无聊

## 字符串是否应该可变？

字符串需求非常多，99%都是小的不可变的，因此cow也有存在价值，SSO默认都做

fbstring也有长短串优化， 甚至还有umbrastring这种prefix优化字符串

回到问题，看需求，c++是灵活的，面对不同需求解法多花样多，就是图这个花样我才学c++


## struct vs tuple?

永远优先struct，tuple只适合转发，没有名字信息是致命的

## 如何调试模版错误？

只能复制编译报错拿出来二分，搜代码文件名字，瞪眼法，没有好的办法。如果ICE就放弃吧

## ICE/NTTP/....是什么

关于这些缩写名次 https://quuxplusone.github.io/blog/2019/08/02/the-tough-guide-to-cpp-acronyms/

这里有个总结。其实看一遍大概就明白了

## 有没有c++推荐书单/怎么学c++

书单 Stackoverflow上有个经典书单 https://stackoverflow.com/questions/388242/the-definitive-c-book-guide-and-list

说实话，你不太可能挨个看完，这里列一下

- c++ primer 第五版，是举例写代码，书很厚习题很多，我曾就有过，没看完送人了。作者也去世了，永远停在c++11
- Programming: Principles and Practice Using C++ 这本是BS老头的书，写的例子非常多，这个值得看。跟着写
- A Tour of C++ BS发牢骚，没啥意义不用看
-  Accelerated C++ 老东西，不用看
-  Effective C++/More Effective C++/Effective STL 这里面的经典条目，你直接看一下标题看一下代码就行了，搜一下到处都是，属于常识性的东西
-  Effective Modern C++ 讲c++14的，也没啥新东西，可以看看条目和代码
-  Exceptional C++/More Exceptional C++/Exceptional C++ Style 异常安全，如果你不知道，你可以跳过
-  C++ Coding Standards 什么101条经验，和前面的effective重复，看不看都行
-  C++ Templates: The Complete Guide 库作者可以看，其他人可以跳过
-  C++ 17/20 - The Complete Guide 不用看。手册
-  C++ in Action 不用看
-  Functional Programming in C++ 这个叫c++函数式编程，这个方向就这么一本书，鉴定为看一乐，没用
-  Modern C++ Design 现代C++程序设计，这本是AA的天书，讲策略模版的，代码已经很老了，不如直接看Folly文档学的快
-  C++ Template Metaprogramming 纯纯的糟粕，看一眼后悔五天
-  C++ Concurrency In Action c++并发实战 这本说实话有点入门，看一乐，讲的atomic和线程池之类的玩意，帮你理解语义，但你看了也看不太明白，很晦涩
-  Advanced C++ Metaprogramming 这本我就看了十几页就看不动了，天书
-  Large Scale C++ volume I, Process and architecture  大规模c++程序设计，这本书还是挺不错的。推荐一看
-  C++ Software Design 这本我还没看完，看完发表意见
  
还有一些老书什么深入理解对象模型stl源码剖析之类的 ，我只能说开卷有益，但没事你别开这几卷

至于怎么学c++，永远是围绕着需求来的，你要先有一个目标，需求，做什么，然后围绕这个目标努力，然后围绕这个目标迭代你的代码

光看不写是不行的，纸上得来终觉浅

这里有一篇详细的介绍，不是我写的，但是很不错，给新人参考 https://zclll.com/index.php/cpp/get_started_cpp.html

## 编译器之争？哪个编译器好

需求需要用什么编译器就用什么，gcc/clang也可以自由选择使用libcxx还是libstdc++

你也可以全平台都用

举例 clickhouse就选择使用libcxx和llvm compilerrt来作为项目一部份

## xx算法/xx设计比标准库stl快，为什么没有进标准库，有没有可能进标准库

introsort不如pdqsort，pdqsort有机会，但目前演进很慢

还有fmtlib的浮点数要比标准库的快

还有令人诟病的regex问题。cxx标准库为了ABI稳定做了太多妥协，当然他们也懒得一笔

能用第三方库就用，c++生态问题一直非常令人诟病，而其他快的库/算法/设计可能由于信息差的问题看不到

关注c++中文周刊，谢谢

## 有没有初学者入门推荐的视频

教学视频通常信息量过低，我个人不太推荐，如果非要看可以B站随便搜入门视频

另外CPPCON建议学一些之后再看。

对于初学者，开卷有益，随便找一本书看起来再说

另外很多人买网课，属于一种健身房办卡的行为，靠花钱激发负罪感都花钱了得学得练

这种心态也能理解

当然你也可以给我打钱

## int8为什么std::cout无法打印

有一些字符是不可见字符，std::cout不会按照int打印

这种场景选择用fmt


## 感觉clang-tidy/告警报错很有挫败感，感觉自己老也写不对

不要陷入教条主义，告警尽量修

clang-tidy很多是最佳实践，做不到，能控制住影响，也可以忽略掉 NOLINT

专家还建议每天八杯水呢。尽力而为，控制影响，要有自己的判断


## optional<T*> 是好的设计吗

非常不好

## 为什么vector bool不建议使用

vector bool不是vector 这个比较违反直觉。原来在stl实现是不叫vector bool

做了proxy帮你封装pack了数据，但是却违反了vector的直觉使用，非常糟糕的设计

非要用，使用deque bool vector int都可以。

在乎字节，用bitmap/bitset，甚至roaringbitmap