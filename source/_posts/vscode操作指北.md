---
title: vscode操作指北
date: 2022-03-04 10:23:23
cover: https://s2.loli.net/2022/03/04/U3ocLgxXV4ANR5j.png
tags:
  - vscode
categories: IDE
description: vscode入门指北，从零到C的Hello World，还包括一些常用操作。
---

# Visual Studio Code操作指北

## 介绍

[vscode的官方地址。](https://code.visualstudio.com/)

vscode是由微软团队推出的一款**开源**的**代码编辑器**。

## 下载及安装

### 下载

[官方下载地址。](https://code.visualstudio.com/)

### 安装

下载完成后，双击运行开始安装：

1. 选择同意此协议，下一步；
2. 选择你希望安装的目录，下一步；
3. 可以更改你希望的开始菜单名或禁止创建开始菜单，下一步；
4. 各个选项按你自己需要选择，**通常情况下默认即可**，下一步；
5. 开始安装，等待完成即可。

## 快速开始

### 安装中文

第一次运行vscode时，右下角通知有提醒，可以直接**安装并重启**，界面就变成中文了。

![image-20211025203252544](https://oss.chundot.xyz/picgo/image-20211025203252544.png)

或者你可以点选左侧工具栏的**扩展(最下面)图标**，搜索框输入Chinese，安装安装次数最高的那个语言插件并重启。

![image-20211025203716083](https://oss.chundot.xyz/picgo/image-20211025203716083.png)

### 创建第一个项目

你可以随意的选择一个你希望保存你所有代码的目录，创建一个新的文件夹，在vscode中单击**文件**--**打开文件夹**选择新创建的文件夹并打开。

然后选择**是，我信任此作者**即可。

![image-20211025204559387](https://oss.chundot.xyz/picgo/image-20211025204559387.png)

### 项目内创建文件夹或文件

点选左侧工具栏的**资源管理器**选项卡，或按下默认的快捷键：`Ctrl + Shift + E`。

红框四个图标代表新建文件、新建文件夹、刷新资源管理器，折叠文件夹(文件夹内容较多时有用)。

你也可以右击**蓝线**内区域进行操作。

![image-20211025211048557](https://oss.chundot.xyz/picgo/image-20211025211048557.png)

我们可以先新建一个`index.html`。

![vscode-new-file](https://oss.chundot.xyz/picgo/vscode-new-file.gif)

### 编辑代码

你可以单击或双击**资源管理器的文件**使其显示在编辑器中。点选我们刚创建的`index.html`(可能已经打开了)，在右侧即可开始编写代码。

对于HTML和CSS，vscode内置了[emmet](https://emmet.io/)，非常高效的前端**代码片段**合集。**我们之后将会更加详细讲解这部分功能**。

[在这里查阅emmet的奇技淫巧！](https://docs.emmet.io/cheat-sheet/)

![vscode-emmet](https://oss.chundot.xyz/picgo/vscode-emmet.gif)

当然，其他的语言也会有高效的代码片段，你也可以在**扩展**中找到各式各样的代码片段包！

### 常用插件

#### One Dark Pro

![image-20211026153717317](https://oss.chundot.xyz/picgo/image-20211026153717317.png)

个人比较喜欢的编辑器配色插件。有三种方案可选。

当然，vscode有好几种自带的配色方案，如果你觉得自带够用，你完全可以不安装这个插件！

![](https://cdn.jsdelivr.net/gh/binaryify/onedark-pro/screenshots/normal.png)

#### vscode-icons

![image-20211026153649933](https://oss.chundot.xyz/picgo/image-20211026153649933.png)

非常棒的图标库，为vscode添加及更新了许多文件和文件夹的图标（文件根据后缀名，文件夹根据名称自动更改图标）。

![image-20211026153545952](https://oss.chundot.xyz/picgo/image-20211026153545952.png)

## 常用环境配置

### C/C++

#### gcc方案

##### 下载mingw64

Windows是不带的，为此我们需要下载mingw64。

[在这边下载mingw64。](https://sourceforge.net/projects/mingw-w64/files/mingw-w64/)

下载一个**MinGW-W64 GCC-8.1.0**选项下的即可，比如**x86_64-posix-seh**。

[关于各个版本的说明。](https://www.pcyo.cn/linux/20181212/216.html)

##### 配置path

下载完成后将压缩包中的mingw64文件解压到你希望的目录（记得安装**7zip**等**解压缩软件**）。

**本文将其解压至C盘根目录**，此时我们需要的路径名为`C:\mingw64\bin`。

接下来：

1. 资源管理器左侧右击**此电脑**（win7为**计算机**）；
2. 点击**属性**；
3. 点击**高级系统设置**（可能在左侧也可能在右侧）；
4. 点击**环境变量**；
5. 找到**PATH**点**编辑**（系统或用户均可）；
6. 选择**新建**，并添加**刚刚记录的路径**（这里是`C:\mingw64\bin`，**根据你的情况更改**），win7用户注意path之间的**英文分号分隔符**；
7. 确认即可。

按下`WIN + r`键，输入cmd确定，接着在命令行界面中输入gcc测试：

![image-20211026163536250](https://oss.chundot.xyz/picgo/image-20211026163536250.png)

没有出现**"xxx"不是内部或外部命令**就大功告成了！

##### 配置vscode

**记得在path更新之后重启一遍vscode。**

**code runner**是一个方便快速运行各种代码的扩展工具。

扩展面板搜索**code runner**并安装即可：

![image-20211026164625741](https://oss.chundot.xyz/picgo/image-20211026164625741.png)

**cpptools**是微软团队推出的C/C++扩展，在vscode扩展面板搜索**cpptools**，安装：

![image-20211026163805601](https://oss.chundot.xyz/picgo/image-20211026163805601.png)

等待右下角需要的下载完成即可。

##### Hello World!

左侧资源管理器新建一个c文件。

输入下方代码，并`Ctrl + s`保存：

```c
#include <stdio.h>

int main(int argc, char const *argv[])
{
    printf("Hello World");
    return 0;
}

```

**右击**并点击菜单中的**Run code**，或直接按下快捷键`Ctrl + Alt + N`，即可在下方的输出看到**code runner**的执行结果：

![image-20211026165139461](https://oss.chundot.xyz/picgo/image-20211026165139461.png)

**如果你需要在终端输入**，按下`Ctrl + ,`，查找**run in terminal**，为下图的选项打上勾即可：

![image-20211026184454094](https://oss.chundot.xyz/picgo/image-20211026184454094.png)

现在你可以快速运行你的c/c++代码了！

---

##### 运行与调试（cpptools）

除了使用code runner快速运行代码，你也可以通过cpptools**调试运行**代码，这也是cpptools的功能之一。

你可以复制下面的代码到你的c文件中，先使用**code runner**测试：

```c
#include <stdio.h>
#include <string.h>

int main(int argc, char const *argv[])
{
    char sWords[10] = "Hello ";
    char sWho[10] = "Pig";
    strcat(sWords, sWho);
    printf("%s!\n", sWords);
    return 0;
}

```

有没有从终端的输出看到c语言友好的问候呢？

接下来，我们要使用**cpptools**进行调试运行。

你可以在左侧工具栏中找到**运行和调试**的选项，也可以按下快捷键`f5`，并在跳出的文字框中选择**C++ (GDB/LLDB)**。

![image-20211026205842864](https://oss.chundot.xyz/picgo/image-20211026205842864.png)

如果你**PATH配置正确**，选择有**mingw64路径**的选项即可，cpptools会自动生成配置。

![image-20211026205921199](https://oss.chundot.xyz/picgo/image-20211026205921199.png)

接着窗口会跳到launch.json，这是调试的配置，我们可以小小修改下launch.json，**当然也可以关闭不去动它**：

```json
{
    // 使用 IntelliSense 了解相关属性。 
    // 悬停以查看现有属性的描述。
    // 欲了解更多信息，请访问: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "gcc.exe - 生成和调试活动文件",
            "type": "cppdbg",
            "request": "launch",
            "program": "${fileDirname}\\${fileBasenameNoExtension}.exe", //可以选择你希望的路径，但task.json也要改
            "args": [],
            "stopAtEntry": false,
            "cwd": "${fileDirname}",
            "environment": [],
            "externalConsole": false, // 打开外部控制台，根据个人喜好
            "MIMode": "gdb",
            "miDebuggerPath": "C:\\mingw64\\bin\\gdb.exe",
            "setupCommands": [
                {
                    "description": "为 gdb 启用整齐打印",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                }
            ],
            "preLaunchTask": "C/C++: gcc.exe 生成活动文件",
            "internalConsoleOptions": "neverOpen" //不自动打开调试控制台
        }
    ]
}
```

task.jsonz在这里是用于生成可执行文件的，一般不用改。

我们可以再次运行一次，查看**终端**：

![image-20211026220616228](https://oss.chundot.xyz/picgo/image-20211026220616228.png)

确实有结果，但前面有很长一段命令，观感糟糕！只是为了查看程序运行结果还是用**code runner**更好！

接下来我们尝试**调试**，光标移到第8行的标号左边点击，可以给这一行打上断点：

![image-20211026220756870](https://oss.chundot.xyz/picgo/image-20211026220756870.png)

我们再按下`f5`调试运行，此时我们进入了调试状态，程序停止在断点处：

![image-20211026221211430](https://oss.chundot.xyz/picgo/image-20211026221211430.png)

- 左侧**变量**区可以查看变量状态，**监视**可以另外添加你所需要查看的变量；
- 标黄代码行是当前执行到的代码处；
- 上方的操作栏：
  - **继续**`f5`，程序继续运行，直到下次碰到断点时再挂起；
  - **单步跳过**`f10`，运行一行，不会进入，保持挂起状态；
  - **单步调试**`f11`，运行一行，进入方法内部（一般只会进入自定义方法），保持挂起状态；
  - **单步跳出**`Shift + f11`，继续运行直到从方法内部跳出，保持挂起状态；
  - **停止**和**重启**就是字面意思。

调试运行的速度相对较慢，只推荐代码出问题，需要调试代码的情况使用。

#### clang方案

##### 等待补全...



## 常用快捷键

### 编辑或查找快捷键

想要编辑快捷键或查看相关命令，你可以按下`Ctrl + K`再按下`Ctrl + S`。

比如，我想找与括号相关的快捷键，我可以输入bracket模糊搜索：

![image-20211025205452863](https://oss.chundot.xyz/picgo/image-20211025205452863.png)

就找到了！有些操作按键默认留空，你可以为其分配你自己喜欢的快捷键。

---

### 常用快捷键介绍

下面介绍一些比较常用的快捷键。

#### 编辑器操作

##### 保存

`Ctrl + s`

你懂的。当然你也可以在下面提到的**设置**中配置**自动保存**。

##### 代码提示

`Ctrl + i`

有时候vscode的代码建议不会自动跳出。

每当你看不到代码提示感到心慌的时候，就按一下。

![vscode-suggest](https://oss.chundot.xyz/picgo/vscode-suggest.gif)

##### 移动行

`Alt + ↑`将代码向上移动一行。

`Alt + ↓`将代码向下移动一行。

##### 复制行

`Shift + Alt + ↑`或`Shift + Alt + ↓`，方向键决定向上或向下。

![vscode-copy-by-line](https://oss.chundot.xyz/picgo/vscode-copy-by-line.gif)

##### 复制光标

`Ctrl + Alt + ↑`或`Ctrl + Alt + ↓`，方向键决定向上或向下。

要同时对多行进行编辑的时候比较实用。

![vscode-multi-cursor-](https://oss.chundot.xyz/picgo/vscode-multi-cursor-.gif)

#### 其他操作

##### 显示命令面板

`Ctrl + Shift + p`

主题更改，扩展管理，编辑操作，文件格式化……所有命令操作都可以在这里执行。

![vscode-command](https://oss.chundot.xyz/picgo/vscode-command.gif)

## 常用设置编辑

你可以点选左侧工具栏最下方的设置图标找到**设置**选项。

你可以使用快捷键`Ctrl + ,`打开vscode的设置选项。

### XX时格式化

搜索框搜索**Format On**：

![image-20211025212005574](https://oss.chundot.xyz/picgo/image-20211025212005574.png)

比较推荐勾选**Format On Save**，保存时自动使用文件默认的格式化程序。

### 自动保存

搜索框搜索**Auto Save**：

![image-20211027193202773](https://oss.chundot.xyz/picgo/image-20211027193202773.png)

将光标移到选项上下方会有相应的说明，选择你喜欢的就行。

一般不太推荐开启，经常`Ctrl + s`也没有多麻烦。
