# 在linux下折腾EDA安装
最近忽然心血来潮，要搞搞EDA软件安装。EDA软件基本都是linux版本，因此必须要折腾linux了。
这下可就是要折腾个底朝天了。好在本人本着刨根问底的精神，在这个过程中也搞明白了很多事情。如同题目说的，linux目前还是一个折腾人的操作系统。好在有网络，很多问题顺利解决了。
这里就不提软件的安装了，集中提提linux的表现。
先是操作系统版本太高，有的命令不向下兼容，导致需要找个旧版本的命令。这是拦路虎第一个。
其次操作系统版本不匹配，装完之后什么libgcc库的问题，什么libXp的问题，都是从网上找资料一一解决。
再就是装完了，用不了帮助系统。这个网上似乎没人仔细说。先看了看，调的命令似乎是另一个软件的，原来path里另一个软件在前。改了之后还不行。再看，网上说了，旧软件调的是netscape，早就不存在了，做个link。还不行。于是进到这个命令里，原来是脚本，于是一行一行的debug（这点好，自己的机器自己想怎么办就怎么办，单位的软件有问题，IT可没那么多耐心），最后发现还是库的问题，于是缺版本的就补上，路径不对的就调整顺序，总算是自己搞定了。
总结一下，其实我这还算好的，主要问题一个是操作系统的兼容性，包括不同命令的不向下兼容，不同系统包含命令的不同，不同版本所带的库不同。另一个问题就是缺库，或者说缺so文件，或者so文件版本不对。这个问题又由于找库的路径设置，以及操作系统环境变量的设置，变得极为复杂。A用了B，要么是系统里没有B，要么有B，但有好几个，结果由于LD路径设置的问题（有的软件自己启动时又重新设置LD），导致找到的B版本不对。知道了这些问题，解决起来还算顺利。就是总担心自己不停的给这个软件修so文件的bug，会不会影响到其他软件。
回想一下，window早期其实也有这些问题，当年dll也时不时缺。不过现在基本没这些事情了。linux看着是一家，其实类比到windows，也相当于从win95到win8了。要让所有软件能不修改的运行在win95到win8，估计同样是不可能的。
其实只要把库给对了，linux的软件运行起来基本还是正常的，可是这个给对就比较困难了。不同软件可能需要的并不以一样，却要同时运行。单位上后来是给不同软件运行启用不同的环境。自己在家里想搞个傻瓜的，觉得主要问题还是出在path设置上，path等于设置了寻找文件的优先级，自然对不同软件就地位不同。
现在linux又有yum，apt等智能管理软件的工具。可是这些东西都是管理升级用的，似乎并不适合我的情况。到后来我都是只要需要的so文件，然后直接扔到自己目录下。这有些像全局变量和局部变量的关系。全局变量用多了总是担心会影响到其他东西，还是局部变量可靠些。
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
这两天又碰到一个新的奇怪问题，把解决方案写在这里也许可以帮助有的人。
现象：新拿到的一台机器，使用icfb时开ade很慢，关icfb也很慢，会报无法连接到wavesan，或者是mps session error之类的错，而且时好时坏。后来发现是和网卡有关，当网络有连接时正常，否则就有问题。仔细看了看进程，发现wavescan的mpshost与其他icfb里进程名称不同。我的机器名是a.b形式，其他icfb进程，如libmanager的命令行中都是mpshost a.b，只有wavescan是mpshost a。icfb之间的进程通讯都是走ipc，也许就是因为mpshost的名称不对造成了无法通讯。再进一步追查，在联网时，nslookup可以找到a的ip，而且是127开头（因为在dns设置中有search b的选项，就是会自动将a转为a.b，dns自动在外网中查询，居然查到了一个）。在不联网时，就无法找到a对应的ip。于是修改hosts文件，将a也手动添加进去，于是问题解决。唯一奇怪的就是为什么wavescan会在被调用时用a作为mpshost的名字。
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 

