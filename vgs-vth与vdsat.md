# VGS-VTH，VDSAT与V*
cmos模拟电路设计者的常见困惑之一就是vgs-vth怎么不等于vdsat。为什么要等于？他们会说，这是课本里讲的啊。如果我们再仔细研究课本，就发现各家课本里又在后面说了，由于各种二阶效应，例如速度饱和等，这两者是不等的。那么到底两者是什么关系，为什么是这种关系呢？我们其实应该从头来理清。
对一个mos管而言，他才不管什么vdsat，他只知道vgs。从MIS电容理论那里，又发展出了vth这个物理量。等研究IV曲线时，又发现其实是可以分成两个区域来研究的，线性区和饱和区。那么怎么区分这两个区域，人们又找到了vdsat作为区分的标志。从名字上可以看出，这是saturation的vds电压，换句话说，当vds增加到一定程度后，电流不再按照原有趋势增加了，基本保持不变了。所以这是这几个值的原始定义。
从这也可以看出，我们未必需要vdsat电压这个定义，比如有些model里觉得IV曲线不应该这么划分区域，以致仿真常常不连续，在那种model里就没有vdsat的位置存在。
mos的IV曲线是客观的，但怎么描述却是有点主观的，不同人喜欢不同的近似方法，因此就出现了不同的model。大部分model都是从一个1/2u*cox(vgs-vth)^2发展出来的。这个model就是level1 模型。在这个最简化的模型里，自然有vgs-vth=vdsat。这也是我们课本一直在重点讲的图像。但这个模型有点过于粗糙，后面就发展出了许多新的修正。注意只是修正而已，大的框架还是在此基础上。这些新的模型就有了不同的名字，level2，level3，bsim3，bsim4等等。但是由于脱胎于level1，所以vdsat依然是决定两个区域的转折点。但是vdsat与vgs-vth却可能不完全一致。
比如从cadence自带的手册可以查到，level2 里的定义就是
 
这是从手册里复制过来的。在其他模型下又不相同。所以如果较真，那vdsat与vgs-vth的关系就好像隔了好几重的亲戚，不同模型下亲戚关系还不一样。但是这亲戚关系也不是无规律的。很多课本上也提了几种重要的修正原理，例如速度饱和。从上面的图片就可以看出，level2对vdsat的修正就分了两种情况：pinchoff和速度饱和。
再仔细看看定义，也还依稀可以在vdsat里看到vgs-vth的影子。
总结一下，vgs-vth=vdsat是最简单模型里的关系式。vdsat的作用是用来划分饱和与线性区域的，在不同模型下他有着不同的表达式，与vgs-vth只有间接的关系，甚至在有的模型里由于不区分不同工作区域，就没有vdsat这个变量存在。
现在说说另一个指标v*。这个东西没有统一的叫法，所以先从定义开始说起。mos用在模拟电路里最重要的参数就是gm，由于功耗也很重要，所以另一个重要参数是I。往往人们需要用功耗换速度，I越大gm越大，但作为讲性价比的工程师就想到了参数I/gm。在简单模型里，可以很容易推导出gm=2I/vdsat，所以vdsat=2I/gm。在复杂模型里，2I/gm与vdsat没有了直接关系，但是仍然可以定义2I/gm作为一个相似的电压值，有人就叫他V*。
这么看起来V*其实与模型关系不大，不论什么样的模型都可以计算出V*，不像vdsat，在有的模型里就不存在。V*的一个特点就是在从饱和区向亚阈值区变化时，V*先变小再接近不变，这说明一个管子在接近亚阈值区后性价比较高，但是进一步降低vgs-vth意义就不大了。
现在看起来，我们就有了vdsat，v*，vgs-vth这三个变量，其实还有一个vgseff，这是模型里用于计算的一个中间变量。在简单模型里他们是一样的，在其他模型里就没有直接关系了，其含义也是各有不同。不过如果去做参数扫描，就会发现这几个值在亚阈值区和饱和区是接近的。特别的，用我手头几个模型可以发现一些其他规律。1.如果考虑速度饱和，vdsat按理会小于vgs-vth，但实际并不一定如此，说明还需要用其他效应来解释。2. vgseff与vgs-vth是最接近的。3. V*与vgseff也很接近，只有vdsat偏离的较远。V*与vgseff比较接近，在level2的模型里可以得到相对容易的解释，就留给大家自己琢磨了。
 

 

