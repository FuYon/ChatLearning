## ChatLearning

让你的bot学习你的群聊

------

## 开始使用

**ChatLearning**的运行基于<code>mirai-api-http</code>，使用前请先下载[mirai-api-http](https://github.com/project-mirai/mirai-api-http)并完成配置

在<code>data.json</code>文件中填入<code>mirai-api-http</code>的配置信息，请使用<code>http adapter</code>，并确保<code>singleMode</code>为<code>false</code>

```json
{
 "Key": "xxxxx", //在mirai-api-http中设置的密钥
 "host": "127.0.0.1:8080", //mirai-api-http中设置的地址（若设置成0.0.0.0，请填写127.0.0.1）
 "port": "8080", //mirai-api-httpmirai-api-http中设置的端口
 "qq": "xxx",  //所登录mirai的QQ号
 "session": "xxx" //任意，由程序自动获取
}
```

**Windows**用户点击<code>Chatmain.exe</code>运行

**Linux**用户则使用python运行<code>Chatmain.py</code>脚本 **（python版本需为3.5以上）**

输入<code>help</code>来查看命令列表

## 依赖

本项目所使用的一些Python模块：

<code>asyncio </code>   <code>prompt_toolkit</code>   <code>nest_asyncio</code>   <code>threading</code>

以上模块**Linux**用户可能会缺少，请使用<code>pip install</code>来安装对应模块

## Q&A



**Q：ChatLearning**的功能是什么？

**A：ChatLearning**可以自动的从群聊中收集聊天记录，并且将这些聊天记录整理成一个**问&答**的词库，当有人发送的消息与词库中的”**问**“匹配时，会从“**答**”中随机抽取其中一个回复在群聊中

------

**Q**：打开软件后，我应该如何使用？

**A**：首先应添加需要bot记录的群号，然后开启记录功能（输入<code>help</code>可查看到对应指令）

------

**Q**：要收集多久bot才会开始回复呢？

**A**：收集的时间完全由自己决定，理论上时间越久，效果会更好且更加有趣

------

**Q**：我要怎么才能让bot回复？

**A**：首先应添加需要bot回复的群号，然后开启回复功能（输入<code>help</code>可查看到对应指令）

------

**Q**：什么是全局模式？

**A**：未启用全局模式时，bot只会回复所对应群中收集的词库（这个是实时生效的，上一秒从群中收集到词库，下一秒就可以在本群中回复这个词库了），当开启全局模式时，bot只会从**ChatLearning周期性**整合的从所有群收集到的**总词库**中回复相应数据，你可以**自行调整这个周期**的时间，并且你也可以选择不让某些群的词库被整合进这个**总词库**中

------

**Q**：什么是词库链间隔时间？

**A：ChatLearning**将第一个人的消息定义为一个词库链的头，他的消息只会被记录为问题，不会被记录为答案，而第一个人在**ChatLearning**中的定义是间隔一定时间无人发言后，**第一个发言的人**，你可以自行调整这个间隔时间，默认为900秒

------

**Q**：什么是管理模式？

**A**：在这个模式中，你可以删除一些你觉得需要删除的回复，首先需要设置管理员QQ

------

**Q**：为什么管理员QQ只能设置一个？

**A**：懒，如果有需求的话后续版本可以更新

------

**Q**：目录下的<code>.cl</code>和<code>.clc</code>文件是什么，我可以删除它吗？

**A**：<code>.cl</code>文件是**ChatLearning**所缓存在本地的词库，它的文件名就是所对应的QQ群号，如果你觉得不需要这个词库了，可以在**ChatLearning**退出后将它删除。<code>.clc</code>文件是**ChatLearning**的配置文件，删除后**ChatLearning**会随即崩溃

------

**Q**：目录下的<code>.cl</code>文件太大太占空间了怎么办？

**A**：一般来说不是每天都隔一会99+的群聊，是不会很占空间的， 目前只能选择进入管理模式手动清理一些不需要的回复，后续会更新根据记录的时间批量删除







