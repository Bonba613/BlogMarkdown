# GitHub拉取的python项目无法运行排错_2022-11-08

在Shell 中输入：python --version	

Shell 返回结果：Python 2.7.16	# 需要更新最新的Python版本

解决：

> Mac Python下载安装教程
>
> https://zhuanlan.zhihu.com/p/363048202

> 下载链接：
>
> Python 发布 Python 3.11.0 |Python.org
>
> https://www.python.org/downloads/release/python-3110/



重新安装Python最新版本后，输入：python3

返回：Python 3.10.7



输入：print('hello worth')	

返回：hello worth



输入：pip3 install numpy

返回：`File "<stdin>", line 1   pip3 install numpy     ^^^^^^^ SyntaxError: invalid syntax`

解决：

> pip指令出现SyntaxError: invalid syntax的两种原因及解决方法，完美解决！
>
> https://blog.csdn.net/lzRush/article/details/114213053
>
> > 一、第一种报错如下
> >
> > >>> pip install numpy
> > >>> File "<stdin>", line 1
> > >>> pip install numpy
> > >>>  ^
> > >>> SyntaxError: invalid syntax
> > >>> 原因：在Python运行环境里执行pip指令是错误的
> >
> > 解决：在CMD中或者Anaconda Prompt中运行pip即可



再次输入：pip3 install numpy

返回：

```shell
Collecting numpy
  Downloading numpy-1.23.4-cp310-cp310-macosx_10_9_x86_64.whl (18.1 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 0.2/18.1 MB 23.5 kB/s eta 0:12:42
```

`# 成功运行‘pip3 install numpy’命令`

返回：

```shell
Installing collected packages: numpy
Successfully installed numpy-1.23.4

[notice] A new release of pip available: 22.2.2 -> 22.3.1
[notice] To update, run: pip3 install --upgrade pip
```



输入：python --version

返回：Python 2.7.16



> Mac 上如何正确的安装Python2.7和Python3
>
> https://www.jianshu.com/p/c0debdf9d629



> STEP 1 安装Xcode
>
> 安装完成后 安装 Xcode command line tool
>
> `xcode-select --install`

输入：xcode-select --install

返回：`xcode-select: error: command line tools are already installed, use "Software Update" to install updates`

解决：

> Command Line Tools安装方法
>
> 原文链接：https://blog.csdn.net/More930/article/details/78717764
>
> > 验证安装成功没有:
> >
> > 在输入xcode-select --install
> >
> > 如果出现如下,说明安装成功了
> >
> > xcode-select: error: command line tools are already installed, use "Software Update" to install updates

`# 说明xcode安装成功了`



> STEP 2 安装Homebrew

输入：brew -v

返回：

```shell
Homebrew 3.2.15
Homebrew/homebrew-core (git revision 74368c3b395; last commit 2021-10-06)
Homebrew/homebrew-cask (git revision 2abf4b529e; last commit 2021-10-06)
```

解决：

> MacOS系统使用Homebrew官方地址
>
> https://blog.csdn.net/fgx_123456/article/details/109529180
>
> > 查检安装结果：
> >
> > brew -v
> >
> > 如果能正确打印版本信息，则安装成功！



> STEP 3 安装Python
>
> 接下来要正式进入安装Python的步骤了！
> 首先，输入
>
> `python --version`
> 会有如下结果：

输入：python --version

返回：Python 2.7.16



> 这是Mac系统要使用的Python，不去动它。所以现在我们要用homebrew来安装自己使用的Python。
>
> 利用homebrew搜索Python
>
> `brew search python`

输入：brew search python

返回：

```shell
==> Formulae
app-engine-python          python-launcher            python@3.8
boost-python               python-markdown            python@3.9 ✔
boost-python3              python-tabulate            reorder-python-imports
bpython                    python-tk@3.10             wxpython
gst-python                 python-tk@3.9              pythran
ipython                    python-yq                  jython
micropython                python@3.10                cython
ptpython                   python@3.7
==> Casks
awips-python                             mysql-connector-python

If you meant "python" specifically:
It was migrated from homebrew/cask to homebrew/core.
```



> 开始安装：
>
> `brew install python`

输入：brew install python

返回：

```shell
Updating Homebrew...
==> Homebrew has enabled anonymous aggregate formula and cask analytics.
Read the analytics documentation (and how to opt-out) here:
  https://docs.brew.sh/Analytics
No analytics have been recorded yet (nor will be during this `brew` run).

==> Homebrew is run entirely by unpaid volunteers. Please consider donating:
  https://github.com/Homebrew/brew#donations
Warning: python@3.9 3.9.7 is already installed and up-to-date.
To reinstall 3.9.7, run:
  brew reinstall python@3.9
```

`# 按照提示输入‘brew reinstall python@3.9’`



> `brew install python3`
> 如图所示，表示python3安装成功

输入：brew reinstall python@3.9

返回：

```shell
...
==> /usr/local/Cellar/python@3.9/3.9.7/bin/python3 -m ensurepip
==> /usr/local/Cellar/python@3.9/3.9.7/bin/python3 -m pip install -v --no-deps -
==> Summary
🍺  /usr/local/Cellar/python@3.9/3.9.7: 3,080 files, 54.7MB
```



> 查看安装的目录
>
> `open /usr/local/Cellar/`

输入：open /usr/local/Cellar/

弹出finder窗口，且存在：‘ /usr/local/Cellar/python@3.9/3.9.7/bin ’路径



> STEP 4 设定路径$PATH (不和系统Python干扰)
>
> 什么是路径$PATH呢？
>
> 还记得我们在装Python的时候，输入了brew，
> 系统就自动会知道要开始跑homebrew。
> 系统到底怎么知道我们的brew在哪里？
> 这就是$PATH的用途了！
>
> `echo $PATH`

输入：echo $PATH

返回：

```shell
/Library/Frameworks/Python.framework/Versions/3.10/bin:/usr/local/bin:/usr/local/sbin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/Library/Maven/apache-maven-3.8.4/bin:/usr/local/mysql/bin:/Users/Yaya/Library/Android/sdk/tools:/Users/Yaya/Library/Android/sdk/platform-tools
```

`# 说明存在$PATH文件，且该文件能正常读取`



输入：emacs --version

返回：sh: emacs: command not found

<!--# 说明还没有安装emacs-->

解决：

> 工欲善其事，必先利其器之—MAC下安装与配置emacs
>
> https://blog.csdn.net/SCHOLAR_II/article/details/80976314
>
> > mac os下安装emacs有如下方式 
> > * 通过homebrew安装
> >
> > brew install emacs



再次输入：emacs --version

返回：

```shell
GNU Emacs 27.2
Copyright (C) 2021 Free Software Foundation, Inc.
GNU Emacs comes with ABSOLUTELY NO WARRANTY.
You may redistribute copies of GNU Emacs
under the terms of the GNU General Public License.
For more information about these matters, see the file named COPYING.
```

<!--# 说明emacs安装成功-->



输入：exit	# 退出root状态

返回： ~ % 	# 当前处于用户态

> Mac切换到root用户（su命令行），以及退出
>
> https://blog.csdn.net/liujingjie2010/article/details/82888381



> 所以现在的问题就是，系统在/usr/bin里面也有一份Python
> 现在我们在/usr/local/Cellar里面也装了Python
> 这样在terminal打上python指令时，谁会被开启呢？
> 因为路径有顺序，所以它会先找到系统的Python
> 现在就要来解决这个问题
>
> `sudo emacs /etc/paths`
> sudo让我们取得管理员权限
> 用emacs这个程序编辑路径档案
> terminal会要求输入密码

输入：sudo emacs /etc/paths

返回：# 要求输入密码

键入密码后返回：

```shell
/usr/local/bin
/usr/bin
/bin
/usr/sbin
/sbin
```



> 如果不是这个顺序，调整成这个顺序。
>
> control + k：把一行字剪下来
> control + y：把字粘贴
> control + x + s：存盘
> control + x + c：关掉emacs

输入：control + x + c	# 行顺序没有问题，关闭emacs



> 这时，重启terminal 会看到变化，再打一次
>
> `echo $PATH`

重启Terminal终端

输入：echo $PATH

返回：

```shell
/Library/Frameworks/Python.framework/Versions/3.11/bin:/Library/Frameworks/Python.framework/Versions/3.10/bin:/usr/local/bin:/usr/local/sbin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/Library/Maven/apache-maven-3.8.4/bin:/usr/local/mysql/bin:/Users/Yaya/Library/Android/sdk/tools:/Users/Yaya/Library/Android/sdk/platform-tools
```



输入：which python3

返回：

```shell
 File "<stdin>", line 1

  which python3

     ^^^^^^^
```

解决：

<!--# 在Python运行环境里执行‘which python3’是错误的-->



输入：quit()	# 退出Python环境

返回： ~ % 	# 当前处于用户态

> python-mac terminal终端怎么退出python命令行
>
> https://blog.csdn.net/weixin_44454306/article/details/101233255
>
> 
>
> > 使用 quit(), exit(), 或者Command+d，或者Command+z退出命令行。



> STEP 5 安装完成，确认结果
>
> 这样就完成啰！
> 其实python3本身比较不会跟其他人打架
> 因为他就是独立的python3
> 所以我们主要是要确认是不是读到我们用brew装的python
>
> `which python`

输入：which python

返回：/usr/bin/python

输入：which python3

返回：/Library/Frameworks/Python.framework/Versions/3.11/bin/python3

<!--# 说明Python3已配置完毕-->



> 如果想使用系统的Python，就输入
>
> `/usr/bin/python`

输入：/usr/bin/python

返回：

```python
WARNING: Python 2.7 is not recommended. 
This version is included in macOS for compatibility with legacy software. 
Future versions of macOS will not include Python 2.7. 
Instead, it is recommended that you transition to using 'python3' from within Terminal.

Python 2.7.16 (default, Aug 30 2021, 14:43:11) 
[GCC Apple LLVM 12.0.5 (clang-1205.0.19.59.6) [+internal-os, ptrauth-isa=deploy on darwin
Type "help", "copyright", "credits" or "license" for more information.
```

<!--说明系统自带的python运行正常-->



输入：/Library/Frameworks/Python.framework/Versions/3.11/bin/python3

返回：

```python
Python 3.11.0 (v3.11.0:deaf509e8f, Oct 24 2022, 14:43:23) [Clang 13.0.0 (clang-1300.0.29.30)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
```

<!--说明python3.11运行正常-->



输入：python

返回：

```python
WARNING: Python 2.7 is not recommended. 
This version is included in macOS for compatibility with legacy software. 
Future versions of macOS will not include Python 2.7. 
Instead, it is recommended that you transition to using 'python3' from within Terminal.

Python 2.7.16 (default, Aug 30 2021, 14:43:11) 
[GCC Apple LLVM 12.0.5 (clang-1205.0.19.59.6) [+internal-os, ptrauth-isa=deploy on darwin
Type "help", "copyright", "credits" or "license" for more information.
```

<!--说明在命令行中直接键入'python',启动的是python2.7版本-->



输入：python3

返回：

```python
Python 3.11.0 (v3.11.0:deaf509e8f, Oct 24 2022, 14:43:23) [Clang 13.0.0 (clang-1300.0.29.30)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
```

<!--说明PATH系统环境变量中存在python3.11。命令行键入‘python3’，启动的是python3.11版本-->



输入：python --version

返回：Python 2.7.16



输入：python3 --version

返回：Python 3.11.0



配置PyCharm环境变量

> MAC环境下pycharm运行Python代码，配置设置
>
> https://blog.csdn.net/weixin_36212725/article/details/121087928
>
> > 下图右面的框就是解释器的位置。
> >
> > Pycharm -> Preference -> PythonInterpreter -> Add
> >
> > 框中的3个选项是区分不同环境下的配置。第一个是通过virtualenv搭建的虚拟环境，第二个是conda Env，是通过conda搭建的环境。第三个是系统的配置环境。
> >
> > 可以根据需要选择。对应的右边有新建虚拟环境和现有的虚拟环境的选项，根据需要选择配置。







输入：pip install setuptools==58.2.0

返回：

```python
  File "<stdin>", line 1
    pip install setuptools==58.2.0
        ^^^^^^^
SyntaxError: invalid syntax
```

解决：

> Windows10使用pip安装地方工具出现SyntaxError: invalid syntax
>
> https://blog.csdn.net/qq_21805743/article/details/123624790
>
> > 需要是在cmd窗口下安装，不是python窗口下。
> >
> > 同时，要找到python的安装目录里的pip所在的路径，并且要命令行cd到该路径下才能进行安装。



