# Mac系统mds、mds_stores、mdworker占cpu很高的解决办法_2023-01-11



> 忽然发现这个mds、mds_stores、mdworker 占cpu很高，然后就搜索了一下，说是可以使用下面的命令给关掉。
>
> sudo mdutil -a -i off
>
> 但是关掉之后，有没有啥负面影响呢，这个东西是干嘛呢？不少文章还提供了这个打开的命令
>
> sudo mdutil -a -i on
>
> > Mac系统mds、mds_stores、mdworker占cpu很高
> >
> > https://blog.csdn.net/qq_27093465/article/details/85275740