# NFS、FTP、SMB、WebDav、DLNA协议详解_2023-01-18

> **FTP 是明文传输安全性不高**，后来又出现了 **SFTP 和 FTPS 等加密传输**。FTP 的特点之一是独立于系统用户组，==只要通讯端口开启就能方便访问，所以特别适合外网共享==，一些老牌共享软件就常常通过 FTP 发布下载链接。
>
> FTP非加密，明文传输，SCP和SFTP是基于SSH的加密，但SFTP支持断点续传，SCP不支持。
>
> SSH、SCP和SFTP都是SSH软件包的组成部分，装了SSH这俩都直接能用。还可以用SFTP把远程文件像本地文件一样操作。
>
> 
>
> 微软又把 SMB 改名为 CIFS（Common Internet File System），并且加入了许多新的特色。
>
> SMB 最早是微软为自己需求设计的专用协议，用来实现微软主机之间的文件共享与打印共享，并不支持在 Linux 上运行。著名黑客、技术大牛 Andrew Tridgell 通过逆向工程，在 Linux 上实现的 SMB / CIFS 兼容协议，命名为 Samba，通过该程序实现了 Windows 和 Linux 之间的文件共享。
>
> 总体来说smb协议的兼容性最好，windows/mac/linux均可支持，各个厂商的电视、盒子和各个手机端的播放器均支持smb协议传输，ftp和webdav原生支持的较少。
>
> 理论上三者速度相差并不大，这里测试的环境是KODI播放器，没深入了解过KODI读取文件的方式，但==大视频文件一定不能用smb协议，杜比视界视频文件一定要用webdav==，咨询过KODI其中的一位开发者，他表示==webdav可以开启多通道读取文件的模式，有利于文件更快的传输==，但并不代表所有播放器的表现都一致。
>
> 想要兼容性好首选smb
> 如果播放器用的==KODI==，不用折腾，==首选webdav==
>
> > NFS、FTP、SMB、WebDav、DLNA协议，傻傻分不清？
> >
> > https://zhuanlan.zhihu.com/p/411161467



<!--群辉等Linux服务器直接使用NFS文件服务即可ss-->

> 在NFS，FTP，SAMBA中，其中下载速度或者说性能最好的是NFS，其次FTP，最后SAMBA
>
> NFS 只能在 Unix 系统间进行共享，而 Windows 对其支持很有限。因此有人就在 Linux/Unix 系统中实现了 Windows 文件共享所使用的 CIFS 协议，也叫做 SMB（Simple Message Block）协议。这使得 Windows/Linux/Unix 间可以自由的进行文件共享。
>
> > 文件共享服务 FTP，NFS 和 Samba
> >
> > https://www.cnblogs.com/wxl-dede/p/5042398.html