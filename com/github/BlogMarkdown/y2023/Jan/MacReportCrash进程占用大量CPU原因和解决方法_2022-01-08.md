# Mac ReportCrash 进程占用大量CPU原因和解决方法

当发现Mac系统非常卡时，通过活动监视器发现ReportCrash进程占用的大量CPU资源，高达100%以上。

ReportCrash进程的目的是为了保存应用程序的状态，帮助开发人员了解应用程序崩溃的原因。基本上，流程是启动、崩溃(并调用CrashReporter)，然后重新启动，重复这个循环，永远不会结束。

关闭ReportCrash进程

终端里运行下面两句代码：
launchctl unload -w /System/Library/LaunchAgents/com.apple.ReportCrash.plist
sudo launchctl unload -w /System/Library/LaunchDaemons/com.apple.ReportCrash.Root.plist

打开ReportCrash进程

launchctl load -w /System/Library/LaunchAgents/com.apple.ReportCrash.plist
sudo launchctl load -w /System/Library/LaunchDaemons/com.apple.ReportCrash.Root.plist

> Mac ReportCrash 进程占用大量CPU原因和解决方法
>
> https://www.macdaxue.com/mac-reportcrash/



> Mac ReportCrash 突然功耗增加问题
>
> http://flypig.cc/2021/11/05/ReportCrash/