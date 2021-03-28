# vscode.ide

1. [vscode.ide](#vscodeide)
   1. [在说插件之前,先说vscode的setting](#在说插件之前先说vscode的setting)
   2. [wakatime](#wakatime)
   3. [100 days of code / codetime](#100-days-of-code--codetime)
   4. [gist](#gist)
   5. [Material Theme](#material-theme)
   6. [Go/flutter/dart](#goflutterdart)
   7. [markdown all in one](#markdown-all-in-one)
   8. [codestream](#codestream)
      1. [codestream提供了哪些功能](#codestream提供了哪些功能)
      2. [vscode中如何配置codestream](#vscode中如何配置codestream)
      3. [codestream的工作流程](#codestream的工作流程)
      4. [codestream总结](#codestream总结)

**打造符合自己的vscode环境**

> 什么使用vscode?

- 第一阶段: 工作前几年,主要使用ide,vs201x使用的非常顺畅
- 第二阶段: 转到linux后,主要使用vim,之后一直使用vim
- 第三阶段: 换工作后,没有稳定的linux开发环境,同事推荐了vscode+remote ssh

打造vim环境就变得比较麻烦,vscode提供了基本的补全,对go/c++/dart都有基本的支持,
而且一直期待的github codespace一直不出来,伤心.

其实我个人的需求只有两点:
跨平台迁移成本低(一致性要求高);场景支持丰富(就是对Go/C++/dart有支持).
矮个子里挑个高的:vscode.

> 细说插件之前,先说下插件的安装

vscode提供了两种方式:

- vscode软件本身安装
- 下载插件,从vsix安装

需要注意:有些插件在windows下可从vscode直接安装,但linux下就找不到,
这时就需要第二种安装方式.在这个问题上sync插件并没能帮上.
如果你大部分时候使用的都是单一平台,用sync也是非常推荐的.

## 在说插件之前,先说vscode的setting

下面只说修改项,针对具体插件的修改在描述具体插件时细说.

常用:

- 自动保存,失去焦点就保存
- 字体, 'Courier New',  '微软雅黑', monospace
- 字号, 18
- tab大小, 2

文本编辑器:

- 打开文件时自动检查tab和空格
- 行号, 相对行号
- 折叠, 总是显示
- 平滑滚动
- tab补全
- 复制时格式化
- 保存时格式化
- 输入完一行后,自动格式化

工作区:

- 历史命令,500

功能:

- 终端,选中即复制

## wakatime

这是一个时间跟踪工具,安装之后按指引配好api key.
默认会在状态栏显示wakatime的统计信息,点击就会打开网页显示详细信息.

## 100 days of code / codetime

codetime是另一个时间跟踪工具,100 days of code是基于codetime的一个打卡工具.

等这两个插件都安装完后,要先用codetime来注册登录帐号,
注册一步就搞定,但在vscode上的登录,试了很多次都不行,
最后先在100 days of code中触发登录,后来才能从codetime中登录,
具体是不是这个逻辑我也不确定,反正最后都登录上了.

这两个工具的使用,很多都是交叉的,比如说100上要提交log,需要有project,
这个project是从codetime中来的,还有里程碑/徽章等.

如果仅仅是简单点用,可以用codetime来跟踪时间,用100 days of code来跟踪打卡.
如果要使用一些project等有价值的辅助工具,还不是免费的,偏离了初衷.

## gist

非常强大的代码片段服务,除了放代码片段,也可以放笔记.

这个在windows上可直接从vscode安装,在archlinux上需要用vsix安装.
按照指引,需要拷贝一个github的授权token到vscode.

这个插件有一些正确的使用姿势:

- 如无必要,一个gist只放一个文件
- 最好是文本,可以是随笔,博客,笔记,好看的文章,最好不要包含图片
- gist的描述比较重要,多写一点,写具体一点,过滤的时候用多个key会方便很多
- 同一个系列的gist可以用同一个前缀开头,eg: ffmpeg编码深入系列 xxx

## Material Theme

vscode主题,安装这个是因为flutter信仰,总体使用上,还是不如内置的solarized dark主题.

## Go/flutter/dart

这些是语言或框架的支持,后续会针对性补充其他插件.

## markdown all in one

这个是md插件, 最常用的功能是预览(不管是自己写md还是看开源项目,预览都是非常实用的)

Create Table of Contents和 update table of contents用于处理toc,
也就是目录,只要创建了toc,保存的时候会自动更新toc.

在settings中,添加了一个序号,去掉了对github table的转换.

另一个常用的就是将md文件转成html,有时也是非常有用的,eg:md转公众号.

同时介绍另一个插件 open in browser, 这个是在浏览器中打开html文件,
可惜在我的环境中没有成功,不同的平台应该会有更好的表现.

## codestream

这是支持issues/pr的插件,github就是重点支持对象.
同时codestream还对slack等工具都支持的不错,但我们的需求先关注pr/issues.

### codestream提供了哪些功能

由于codestream后面会用的非常多,值得花更多时间来投资.

首先codesteam的目标是协作,特别是远程团队之间的协作和review.
在vscode中就可以使用github discussion.

4大武器: 评论 comment; 反馈 feedback; pr; review.

> codestream中还推出了轻量级的讨论,直接评论就行.
同时轻量级评论还支持github的@系统.

> 另外一个对github无侵入的是轻量级反馈,这是针对pr的.
所以让协作变得更加轻便.这个轻量级的反馈可以理解为pre pr,
最后还是要用github的pr来完成闭环.
review同时也做到了vscode中,这样使用"轻量级评论/轻量级反馈/pr/review"来提高协作效率.

通过codestream,将comment/feedback/pr/review和代码集成到一起,形成了知识库.

### vscode中如何配置codestream

两件事:

- 创建一个账户
- 加入一个team

codestream的协作单元是以team为单位的.

### codestream的工作流程

整个codestream的流程分4步:开始工作/讨论代码/反馈/pr.下面分别描述:

**开始工作**

> 未使用codestream之前的战前准备如下:
> 1. 不管是(修改bug还是新增功能),先要找到相关的issues,指定给自己
> 2. 选择一个issue,变更其状态,表明我们正在处理这个issue
> 3. 切到终端,创建分支
> 4. 通过slack等协作沟通工具,告诉他人我们准备开始处理issue

通过codestream,一键就搞定了.

**讨论代码**

这是基于github discussion的扩展.

*codemark*,就是关于代码的discussion,让评论和某些代码关联起来了.
这些都被保存起来了,好处是新加入的成员可以很容易接触到这些,
codemark也是codestream知识库的基础.
创建一个codemark,就可以基于代码创建一个轻量级的评论.
在comment中,可以对代码进行提问/建议/记笔记等.
创建一个codemark,还可以基于代码创建一个issue.
创建的issue可以丢给github或其他类似的问题跟踪系统.

codemark的生命阶段分"打开/解决/归档",分别是绿色/紫色/灰色.
绿色/紫色是可以直接在vscode编辑页面看到的,灰色只能在codestream中搜索到.
绿色的多,证明了沟通讨论的多,走到解决状态的少.

codemark可以和多段代码联系起来,在描述中可以通过`[#N]`来引用代码片段,其中N是代码片段的序号.
描述中还能添加图片或日志文件,都是为了丰富沟通手段.
和github的做法一样,codemark同样提供了tag.不同的codemark之间也能相互关联.
这些讨论的手段基本和github差不多,但会更加便捷,和代码关联,优势更加明显.

**反馈**

快速反馈除了便于review,还能在未提交的时候就开始沟通.
传统的reveiw是开发的最后一环,快速反馈可以在前期识别风险,优势不是一点点.

每个反馈都会有相应的review. 最终,反馈会升级为pr.

**pr**

开发的最后一环.
最后pr的相关信息,也可以在vscode的编辑界面.

### codestream总结

所有的工作流程都是从issues开始,最后到pr被接受.

codestream也是从issues开始,只是中间加入了不少协作的方法:

1. 从issues挑一个出来处理(修改bug/新增功能),此时会创建分支,标记任务的状态
2. 不停用快速反馈来沟通思路的正确性和实现的正确性
3. 在沟通过程中,可以用codemark来交流或提出新的issue
4. 最后快速反馈被接收,就可以产生pr,走向最后的环节