目录
电路基础篇	3
最基本的概念	4
器件模型	6
小信号模型	8
VGS-VTH与VDSAT	9
交流电容模型	13
电流镜的设计	14
Bandgap设计（一）	16
Bandgap设计（二）	18
OPA与OTA	20
运放：开环与闭环	21
Delta-sigma AD DA设计	23
怎样做FFT	25
AD DA的REF设计	27
ADC的噪声仿真	28
Jitter的定义	29
传输函数的符号化运算	30
版图中衬底如何连接	31
电学噪声	32
信号流图与电路框图	33
EDA使用篇	28
Gui vs cmd	36
ADE simulation 的背后	37
稳定性讨论（三）	38
仿真的意义	40
Gm Id方法的思考	44
接地二三事	45
反馈观点看opa	47
EDA版本相关的几件事	48
一次EMC的debug过程	49
反馈与稳定性（二）	50
提问的学问	52
开关电容中的flick噪声	53
开关电容电路设计	54
反馈与稳定性（一）	55
反馈观点看OPA	57
多级OPA的补偿	59
反馈与稳定性（三）	60
后仿真的经验	62
EDA使用的一些技巧	64
什么时候需要后仿真	66
几件小事	67
谐波参数的设计	68
自己如何做一个蒙特卡洛模型	69
在linux下折腾EDA安装	70
设计思考篇	70
物理学家与数学家；科学家与工程师	73
学而不思则罔，思而不学则殆	74
模拟电路设计的流程	75
科学与迷信	76
个人觉得一些重要的学科	78
 
电路基础篇 
D:\Documents\gaojun\写作\analog IC design\基本概念.doc
D:\Documents\gaojun\写作\analog IC design\器件模型.doc
D:\Documents\gaojun\写作\analog IC design\小信号模型.doc
D:\Documents\gaojun\写作\analog IC design\vgs-vth与vstar.doc
D:\Documents\gaojun\写作\analog IC design\vgs-vth与vdsat.doc
 
D:\Documents\gaojun\写作\analog IC design\电容模型.doc
D:\Documents\gaojun\写作\analog IC design\如何设计电流镜.doc
 
D:\Documents\gaojun\写作\修改\bandgap的设计.doc
 
D:\Documents\gaojun\写作\修改\bandgap设计（续）.doc
D:\Documents\gaojun\写作\analog IC design\ota,opa的设计.doc
D:\Documents\gaojun\写作\analog IC design\运放设计：开环思考闭环仿真.doc
 
D:\Documents\gaojun\写作\修改\delta-sigma系统的设计.doc
D:\Documents\gaojun\写作\修改\AD DA 结果做fft.doc
D:\Documents\gaojun\写作\修改\ad da 中的ref应该有什么样的要求.doc
 
D:\Documents\gaojun\写作\修改\designer guide网站一篇文章的问题.doc
D:\Documents\gaojun\写作\修改\jitter的定义.doc
D:\Documents\gaojun\写作\analog IC design\传输函数的符号分析.doc
D:\Documents\gaojun\写作\analog IC design\版图中的sub和gnd怎么连接？.doc
D:\Documents\gaojun\写作\analog IC design\电学噪声.doc
D:\Documents\gaojun\写作\analog IC design\信号流图与电路框图的一点区别.doc
EDA使用篇
 
D:\Documents\gaojun\写作\修改\gui vs. cmd.doc
 
D:\Documents\gaojun\写作\修改\ADE simulation的背后.doc
 
 
D:\Documents\gaojun\写作\analog IC design\多环路稳定性的一些新思考和新结论.doc
 
D:\Documents\gaojun\写作\analog IC design\仿真的意义.doc
 
 
D:\Documents\gaojun\写作\analog IC design\关于esd.doc
 
D:\Documents\gaojun\写作\analog IC design\关于gmId的一些想法.doc
 
D:\Documents\gaojun\写作\analog IC design\关于接地的二三事.doc
 
 
D:\Documents\gaojun\写作\analog IC design\基于局部负反馈的观点看运放.doc
 
D:\Documents\gaojun\写作\analog IC design\几件和版本有关的事情.doc
D:\Documents\gaojun\写作\analog IC design\一次涉及emc的debug过程.doc
 
D:\Documents\gaojun\写作\analog IC design\接着说说反馈，稳定性.doc
 
D:\Documents\gaojun\写作\analog IC design\仅仅知道个结果是没什么意义的.doc
 
D:\Documents\gaojun\写作\analog IC design\开关电容电路里的1f噪声.doc
 
D:\Documents\gaojun\写作\analog IC design\开关电容电路设计.doc
D:\Documents\gaojun\写作\analog IC design\说说反馈，稳定性.doc
 
D:\Documents\gaojun\写作\analog IC design\对
 
D:\Documents\gaojun\写作\analog IC design\两级放大器有四种补偿方式，三级放大器有四十种补偿方式.doc
 
D:\Documents\gaojun\写作\analog IC design\反馈与稳定性的一些补充.doc
 
 
D:\Documents\gaojun\写作\analog IC design\模拟后仿真的几种做法以及优缺点.doc
 
D:\Documents\gaojun\写作\analog IC design\软件使用方面一些杂七杂八的知识.doc
 
D:\Documents\gaojun\写作\analog IC design\是否需要模拟后仿真.doc
 
 
 
D:\Documents\gaojun\写作\analog IC design\随手记录.doc
 
 
D:\Documents\gaojun\写作\analog IC design\谐波，设计起来不容易.doc
D:\Documents\gaojun\写作\analog IC design\自己做个蒙特卡洛仿真模型.doc
 
D:\Documents\gaojun\写作\analog IC design\折腾linux.doc
设计思考篇 
物理学家与数学家；科学家与工程师
D:\Documents\gaojun\写作\analog IC design\数学家，物理学家；科学家，工程师；.......doc
 
D:\Documents\gaojun\写作\analog IC design\学而不思则罔，思而不学则殆.doc
 
D:\Documents\gaojun\写作\analog IC design\模拟设计的流程.doc
 
D:\Documents\gaojun\写作\analog IC design\科学与迷信.doc
D:\Documents\gaojun\写作\analog IC design\模拟电路设计的几个阶段.doc
D:\Documents\gaojun\写作\analog IC design\个人感觉一些重要的学科.doc
 
D:\Documents\gaojun\写作\analog IC design\一个长期的计划.doc
 
 
 

