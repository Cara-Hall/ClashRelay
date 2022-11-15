# clash relay自动化部署
## 时间线
- 2022-11-9 ~~炫耀~~通过`clash relay`用机场节点当中转
>[Clash relay是真好用，用机场转发Oracle新加坡，电信跑满500](https://hostloc.com/thread-1096161-1-1.html)  
- 2022-11-11 非常详细地介绍了`chash relay`的用法，~~排版太乱，看的头疼~~
>[写了一天的教程！用Clash relay拯救被封小鸡！](https://hostloc.com/thread-1097176-1-1.html)
- 2022-11-13 v2rayN的实现方法，~~简单又复杂哈哈~~
>[一种简单而又复杂的方法实现的转发转发(类似Clash relay)](https://hostloc.com/thread-1097580-1-1.html)

@sakichenan大佬的教程其实非常详细，但是**无法无感自动部署**，
 
另外，由于分流规则直接写进了`yml`配置文件，导致**规则无法在线更新**，

所以有了这篇文章。

## 利用CFW的Parsers实现relay自动化部署
**说明**：基于已有订阅链接，无感添加`relay`策略组<br>

**步骤**：
1. ClashForWindows定位到`Setttings-Profiles-Parsers`，点`Edit`，复制[这段代码](https://raw.githubusercontent.com/Cara-Hall/-ClashRelay/main/parsers.yaml)，粘贴进去，修改自定义节点，保存；

2. 定位到`Profiles`，右键配置文件`Settings`，在订阅链接的`URL`后面添加`#relay`，保存；

3. 更新订阅即可。

## 利用Clash Premium的Rule Providers实现rules自动更新
**说明**：基于`yml`配置文件，添加远程规则，实现在线更新<br>

**步骤**：
1. [下载配置文件](https://raw.githubusercontent.com/Cara-Hall/ClashRelay/main/clash-premium.yml)；

2. 修改`line 22`你的订阅链接，按模板修改`proxies`里自定义节点；

3. 将修改好的配置文件拖入CFW即可使用；

4. 右键配置文件，在`URL`中输入`files://配置文件的本地路径`，即可出现`update`按钮。
