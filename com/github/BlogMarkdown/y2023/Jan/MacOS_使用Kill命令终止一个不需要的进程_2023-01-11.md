# MacOS 使用Kill命令终止一个不需要的进程_2023-01-11



> **杀死一个不需要的进程**。当您确定导致问题或消耗过多资源的进程时，请注意该进程名称旁边的PID列中的数字。要终止该进程，请键入“ kill -9”，后跟PID号。按Enter键。现在将退出问题过程。
>
> > 怎样在Mac上查看和终止进程？
> >
> > https://zhuanlan.zhihu.com/p/93964419



> 这是我在系统上发现的
>
>
> / usr / libexec / sysmond
>
>   /usr/share/man/man8/sysmond.8
>
>   /System/Library/LaunchDaemons/com.apple.sysmond.plist
>
> 它被描述为某种系统/文件监视。
>
> 描述
>        sysmon.conf文件是该文件的主要配置文件。
>        sysmond（man），用于监视各种系统和服务
>        连接到网络的计算机。
>
> > sysmond占用过多的CPU
> >
> > https://mlog.club/article/5290795

<!--sysmond与进程监控有关、活动监视器与sysmond有关-->



出现：kill:kill 373失败：不允许操作

因为：进程拥有root权限，在命令前添加 `sudo` 即可kill进程。



---------------------------------------------------------------------------------------------

参考：

> sysmond过多的CPU使用率
>
> https://qastack.cn/apple/127644/excessive-cpu-usage-from-sysmond