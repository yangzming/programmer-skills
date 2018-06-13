# 程序员小技巧
#### 更新时间 2018/01/07
### 以下为个人学习编程时收集的一些命令，共同学习


## 目录
* [如何阅读源码](#source_code)
* [windows命令](#windows)
* [HTML规范](#html)
* [Linux](#linux)
* [技术模式](#technical_model)
* [Ubuntu简单分区](#ubuntu)
* [MySQL](#mysql)
* [Git](#git)

### <a name="source_code"></a>如何阅读源码
* 安装源码，熟悉其功能和应用方式
* 浏览源码的目录结构
* 分析源码框架，如入口方式，页面间的调用规则
* 熟悉写作风格
* 熟悉数据库和表
* 分析源码
	* 系统架构--入口构造，页面调用方式的具体实现
	* 分析工具和工具函数
	* 怎样实现安全方面的设计
	* 研究模板引擎，从实现方式、效率、易用性开始
	* 研究各个功能模块
	* 研究系统所用到的设计模式
	* 研究对访问压力、执行效率、系统效率、数据库的优化
	
### <a name="windows"></a>windows cmd命令
* calc 计算器
* devmgmt.msc 设备管理器
* mstsc 远程桌面连接
* regedt32 注册表编辑器
* regedit.exe 注册表
* services.msc 服务
* netstat 查看系统端口使用情况
* netstat -ano | findstr 8080
* taskkill /pid pid号
* ctfmon.exe 显示小键盘图标
* systeminfo 查看系统信息
* rononce －p －－－－15秒关机
* dxdiag 诊断工具 查看系统信息
* appwiz.cpl 卸载程序

### <a name="html"></a>HTML规范
* input 里的顺序    
class > id > name > data-* > src > for > type > href > title > alt > aria-* > role

### <a name="linux"></a>Linux
* vim的一些简便操作
    * ctrl + z 从vim转到shell
    * jobs -l 查看在后台的任务
    * fg [任务号] 将任务从后台执行转换到前台执行
    * bg [任务号] 将任务放到后台继续执行


### <a name="technical_model"></a>技术模式
* S.O.L.I.D
    * S – 单一职责原则{一个类应该有且只有一个去改变它的理由，这意味着一个类应该只有一项工作}
    * O – 开放封闭原则{对象或实体应该对扩展开放，对修改封闭}
    * L – 里氏替换原则{在对象x为类型 T 时 q(x) 成立,那么当S是T的子类时,对象y为类型S时q(y)也应成立.(即对父类的调用同样适用于子类)}
    * I – 接口隔离原则{不应强迫客户端实现一个它用不上的接口，或是说客户端不应该被迫依赖它们不使用的方法}
    * D – 依赖倒置原则{实体必须依靠抽象而不是具体实现。它表示高层次的模块不应该依赖于低层次的模块，它们都应该依赖于抽象}

### <a name="ubuntu"></a>Ubuntu简单分区
* hda1 /     10-20G
* hda2 /home 大
* hda3 /boot 200M <br>
       /tmp  5G
* hda5 /swap <2G
* hda6 /var >1G
* hda7 /usr 最大剩余空间的一半

### <a name="mysql"></a>MySQL
* MySQL优化
    * 查询缓存优化
    * 使用EXPLAIN你的SELECT查询
    * 只要一行数据时使用LIMIT1
    * 为搜索字段添加索引(普通索引、复合索引、唯一索引)
    * 避免select * 查询全部 
    * 尽可能使用NOT NULL
    * 使用短索引
    * 不要在列上进行运算
    * 不使用NOT INt和<>操作
    * 永远为一张表设置一个id
    * 使用适当的字段类型
    * 从PROCEDURE ANALYSE()取得建议
    * 把IP地址存成UNSIGNED INT(ip2long()和long2ip())
    * 拆分大的DELETE或INSERT语句
    * 选择正确的存储引擎(InnoDB[写/事务]和MyISAM[读])

### <a name="git"></a>Git
* git init
* git add .
* git commit -m "some log"
* git status
* git log [--pretty=oneline|--graph|--all]
* git reset --hard HEAD^
* git reflog
* git checkout -- file
* ssh-keygen -t rsa -C "email@163.com"
* git push -u origin [<branch name>|<tagname>|--tags]
* git checkout <name>
* git branch [-b|-d|-D]
* git stash [list|pop]
* git remote [-v]
* git tag [-a <name>|-m "log"|-d <tagname>]
* git show <tagname>
* git rm <file>

_Git-questions_
* 如何删除远程tag

        git branch -r -d origin/branch-name
        git push origin :branch-name
        
* 如何解决冲突

        快速合并： git merge <branch-name>
        手动解决冲突，找到<<<<<<<，=======，>>>>>>>，删除旧代码，再去提交

* 如何管理git

        远程分支，即服务端一般有两个，master(线上)和dev(开发)，开发者的分支在本地，开发者完成自己的功能后，提交到自己本地的分支，然后checkout到dev，与个人的分支进行合并
        

        
