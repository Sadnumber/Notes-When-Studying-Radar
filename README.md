# Notes-When-Studying-Radar
使用DCA1000EVM+IWR6843ISK进行ADC数据采集的笔记

一、连接过程

操作流程可以看CSDN的这篇文章：https://blog.csdn.net/touchwith/article/details/130871174?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522168630721516800225524813%2522%252C%2522scm%2522%253A%252220140713.130102334.pc%255Fall.%2522%257D&request_id=168630721516800225524813&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_ecpm_v1~rank_v31_ecpm-1-130871174-null-null.142^v88^insert_down1,239^v2^insert_chatgpt&utm_term=iwr6843%2Bdca1000evm&spm=1018.2226.3001.4187


在连接过程中出现过一些问题：

1、连接时需采用5V3A的电源适配器，低于这个电流可能会导致一些硬件无法正常工作。

2、SetUp DCA1000的这个过程需要在配置完前面所有的内容（如其他地方的连接、天线的配置等）以后，再连接，否则会导致DCA1000ARM点击后出现报错。

3、如果DCA1000的FPGA Version无法读取，需要冷静，这是个非常常见的问题。首先先判断output里是否有报错，有的话按照e2e论坛的几个方法，检查防火墙是否关闭、以太网的IPV4的IP地址是否更改。如果还是不行，尝试重新烧录板子的FPGA。
如果output没有报错，而是卡在一边，这里我建议重新安装mmwave studio软件，个人判断是软件中读取FPGA的这个地方因为某种不确定的操作被修改了，重新安装一次就没问题了。
