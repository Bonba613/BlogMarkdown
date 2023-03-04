# Windows安装Winget_2023-01-13



## 下载Winget



> **备注**
> winget 命令行工具仅在 Windows 10 1709（版本 16299）或更高版本上受支持。
>
> 
>
> **安装 winget 预览版 [仅限开发人员]**
>
> 安装位于 winget 存储库的“Release”页面上的 Windows 桌面应用安装程序包。 安装此包将为你提供 WinGet 客户端，但它不会从 Microsoft Store 中启用自动更新。
>
> 
>
> > 微软官方教程__使用 winget 工具安装和管理应用程序
> >
> > https://learn.microsoft.com/zh-CN/windows/package-manager/winget/
>
> > 【Windows10】使用 winget 工具安装和管理应用程序(转)
> >
> > https://blog.csdn.net/qq2399431200/article/details/106276376



> **位于 winget 存储库的“Release”页面上的 Windows 桌面应用安装程序包**
>
> 项目地址：
>
> https://github.com/microsoft/winget-cli/releases



> Windows Package Manager 1.5.101-preview	# Windows 程序包管理器 1.5.101-preview
>
> https://github.com/microsoft/winget-cli/releases/tag/v1.5.101-preview
>
> > **Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle	# Microsoft桌面应用安装程序**
> >
> > 下载地址：
> >
> > https://github.com/microsoft/winget-cli/releases/download/v1.5.101-preview/Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle



## 安装.msixbundle安装包

> 在.msixbundle安装包目录下按住shift+右键空白处，点击“在此处打开powershell 窗口 (s)” 然后输入：add-appxpackage ./
>
> > 教程地址_msixbundle怎么打开？win10后缀.MSIX安装包怎么安装使用？
> >
> > https://www.jb51.net/softjc/788604.html



也可以将.msixbundle安装包放置在桌面，右键“开始”，选择“ Windows Powershell（管理员）”，`cd C:\Users\用户名\Desktop`

输入：`add-appxpackage ./“包含后缀的文件名”`



## 你可能会遇到如下错误__缺少“Microsoft.UI.Xaml.2.7”

```shell
add-appxpackage : 部署失败，原因是 HRESULT: 0x80073CF3, 包无法进行更新、相关性或冲突验证。 
Windows 无法安装程序包 Microsoft.DesktopAppInstaller_1.20.101.0_x64__8wekyb3d8bbwe，因为此程序包依赖于一个找不到的框架 。请随要安装的此程序包一起提供由“CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US”发 布的框架“**Microsoft.UI.Xaml.2.7**”(具有中性或 x64 处理器体系结构，最低版本为 7.2109.13004.0)。当前已安装的名称为“**Micros oft.UI.Xaml.2.7**”的框架为: {} 
注意: 有关其他信息，请在事件日志中查找 [ActivityId] f30d300b-265e-0001-8388-0ff35e26d901，或使用命令行 Get-AppPackageLo g -ActivityID f30d300b-265e-0001-8388-0ff35e26d901 所在位置 行:1 字符: 1 + add-appxpackage .\Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbun
```



## 缺少 Microsoft.UI.Xaml.2.7.1

> **缺少 Microsoft.UI.Xaml.2.7.1**
>
> 缺少什么就安装什么，可以从下面的链接下载文件，选择系统对应版本的 .𝑎𝑝𝑝𝑥文件使用上面介绍的命令行安装方式进行安装。
>
> > **Microsoft.UI.Xaml.2.7.1 蓝奏云**
> >
> > https://wwm.lanzouw.com/i5NiH04zxiri
>
> **缺少Microsoft.VCLibs**
>
> > 可以从微软官方下载系统对应版本的 .𝑎𝑝𝑝𝑥文件使用命令行进行安装。
> >
> > C++ Runtime packages for Desktop Bridge - Visual C++ | Microsoft Docs
> >
> > https://docs.microsoft.com/en-us/troubleshoot/developer/visualstudio/cpp/libraries/c-runtime-packages-desktop-bridge
> >
> > C++ Runtime packages 蓝奏云
> >
> > https://wwm.lanzouw.com/iwBSb04zy2ub
>
> 
>
> **附加**
> 如果你的电脑是 𝑊𝑖𝑛𝑑𝑜𝑤𝑠10商业版或者是其他精简版本，在安装 .𝑚𝑠𝑖𝑥𝑏𝑢𝑛𝑑𝑙𝑒安装包时可能显示缺少相关的软件框架，以下就是两种情况
>
> **使用软件包管理器进行安装**
>
> 如果需要经常安装𝑚𝑠𝑖𝑥𝑏𝑢𝑛𝑑𝑙𝑒,那么每次使用命令行安装就有一些麻烦了，我们可以使用微软的软件包管理器 (𝑊𝑖𝑛𝑑𝑜𝑤𝑠 𝑃𝑎𝑐𝑘𝑎𝑔𝑒 𝑀𝑎𝑛𝑎𝑔𝑒𝑟)
> 进行安装。
>
> > winget GitHub项目地址
> >
> > https://github.com/microsoft/winget-cli/releases
>
> > Windows Package Manage 蓝奏云
> >
> > https://wwm.lanzouw.com/iUrHk04zwmsh
>
> 
>
> 使用第一种方法完成软件包管理器的安装之后，再次安装 .𝑚𝑠𝑖𝑥𝑏𝑢𝑛𝑑𝑙𝑒文件可以**直接双击进行安装**。
>
> 当然也可以使用 𝑤𝑖𝑛𝑔𝑒𝑡 命令进行查找和安装，这里就不做详细介绍了，具体可以参考以下链接。
>
> > 使用 winget 工具安装和管理应用程序 | Microsoft Docs
> >
> > https://docs.microsoft.com/zh-cn/windows/package-manager/winget/
>
> 
>
> > 教程地址_安装 .msixbundle 文件__准点的星辰
> >
> > https://www.cnblogs.com/last-diary/p/16282118.html



## 安装MSIX打包工具驱动程序

> 1.在“设置”-“应用和功能”-“可选功能”，搜索MSIX，找到“MSIX打包工具驱动程序”点击安装
>
> 2.安装Microsoft.VCLibs.140.00.UWPDesktop框架
>
> 输入以下命令：
>
> `add-appxpackage .\Microsoft.VCLibs.140.00.UWPDesktop_14.0.30704.0_x64__8wekyb3d8bbwe`
>
> 
>
> > **如何安装和更新桌面框架包	# 框架下载地址**
> >
> > 在某些情况下，例如Windows 沙盒或应用程序在脱机计算机上运行时，开发人员可能会发现，从以下链接之一下载与其部署体系结构对应的包并使用 Add-AppxPackage PowerShell cmdlet 手动安装它们会更容易：
> >
> > > Microsoft.VCLibs.x64.14.00.Desktop.appx
> > >
> > > https://aka.ms/Microsoft.VCLibs.x64.14.00.Desktop.appx
> >
> > 
> >
> > > 用于桌面桥的 C++ 运行时框架包
> > >
> > > https://learn.microsoft.com/zh-cn/troubleshoot/developer/visualstudio/cpp/libraries/c-runtime-packages-desktop-bridge
>
> 
>
> 3.安装MSIX包
>
> 代码如下（以安装Microsoft.DesktopAppInstaller 为例）：
>
> `add-appxpackage .\Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle`
>
> 
>
> **总结**
>
> 该方法适用于“ win10 企业版 LTSC ”安装所有的应用商店离线文件，以及msixbundle后缀的安装文件，不需要安装部署应用商店。
>
> 
>
> > 教程地址_win10企业版 LTSC 安装 MSIX（msixbundle) 文件
> >
> > https://blog.csdn.net/weixin_52342227/article/details/125002056



## 你可能会遇到以下错误__系统无法执行指定的程序

重启计算机即可。

重启后，原本.appx或.msixbundle由无图标状态变为“打开的快递箱”图标，说明Windows软件包管理器应用程序成功运行

可以使用`winget -v`验证Winget是否安装成功



## Winget使用方法

> (1)搜索软件
>
> ②winget search 公司名称：这样的命令格式可以搜索某家公司在winget中的软件，比如我们搜索腾讯公司，可以通过命令“winget search tencent”来搜索，马上就会返回相关的搜索结果。
>
> ③winget search 软件名称或ID：这样的命令格式可以搜索相关的软件，比如我们搜索谷歌Chrome浏览器“winget search chrome”。
>
> 
>
> **(2)安装软件**
>
> ②winget install 软件名称或ID -l 指定路径：可自定义安装路径（目录），但是需要软件本身支持这种操作。比如“winget install notepad++ -l d:\notepad++”可将该软件安装在“d:\notepad++”路径下面。
>
> **③winget install 软件名称或ID -i：交互式软件安装。**即在软件下载完成后，需要用户手动进行安装（①②命令无需人工干预）。比如“winget install recuva -i”即可进行通过软件界面进行人工安装。
>
> 
>
> (3)更新软件
>
> winget upgrade 软件名称或者ID：可以对软件进行更新，如输入“winget upgrade notepad++”命令，即可对notepad++进行自动更新。
>
> 
>
> (4)卸载软件
>
> winget uninstall 软件名称或者ID：可以对已经安装的软件进行卸载。如输入“winget uninstall notepad++”命令，即可对notepad++进行卸载。
>
> 
>
> (5)查看软件信息
>
> winget show 软件名称或者ID：可以查看搭配软件的相关信息，比如软件版本、发行方、作者、SHA256、下载链接等。如输入“winget show notepad++”命令，即可查看到非常详细的发行信息。
>
> 
>
> (6)查看已经安装的软件
>
> winget list：可以查看到已经安装在计算机中的软件。如输入“winget list“命令，即可查看到该计算机中已经安装的软件，可看到这些信息包含名称、ID、版本等。
>
> 
>
> (7)帮助命令
>
> winget <命令选项> -?：可以查看某个命令的具体使用方法，帮助使用者快速学习掌握使用。
>
> 
>
> 附加
>
> ①WinGet支持什么系统？
>
> WinGet是微软开发的，仅支持Windows10系统，建议更新到1809以上版本。
>
> <!--Windows10 1809及更新版本-->
>
> ②是否支持自定义安装路径？
>
> winget本身是支持自定义安装路径的，但前提是需要软件（厂商）自己支持。
>
> ④是否有捆绑安装？
>
> 经测试，暂未发现有类似捆绑安装行为。软件通过winget发布前微软/winget项目团队会进行相关审核，以保证质量。
>
> ⑦支持哪些类型的文件格式安装？
>
> 目前支持“.msi”、“.exe”、“.appx”等文件格式的软件安装。
>
> ⑧在Windows中它的同类型产品有哪些？
> 有scoop（链接：github.com/lukesampson… chocolatey（链接：chocolatey.org/）等类似软件。
> ⑨关于下载的网速问题？
> 使用winget下载软件时，由于微软本身并不单独储存某个软件在服务器上，在下载时，winget会指向软件官网的地址。所以在下载某些软件时，可能无法下载、下载速度极慢等都属于正常现象。
>
> 
>
> > 教程地址_WinGet软件包管理工具怎么下载、安装、使用？图文教程来了！
> >
> > https://juejin.cn/post/6976120541518233607





> **参考**
>
> 安装完成使用winget -v验证安装。
>
> 安装路径
> 在GitHub的issue里有不少相关问题，**目前没有设定默认路径的选项，但可以通过参数l指定安装路径**，如下：（随便找了个GitHub上的开源软件）
>
> ps:–rainbow的彩虹进度条看起来很炫
> 另外推荐用参数-i来交互式安装
>
> 默认情况下，诸如list/uninstall等命令都是禁用的，通过winget settings命令打开配置文件可以开启。
>
> <!--修改参数 true/false-->
>
> 总结
>
> 关于源等其他问题建议去GitHub多看看，此项目关注人数也相当多，相信会有解决方法的。windows也在吸收Linux他们的优点，enjoy it
>
> 
>
> > winget 配置安装路径/卸载等指南
> >
> > https://blog.csdn.net/qq_43520571/article/details/115723757

