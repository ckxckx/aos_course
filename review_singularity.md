# Report of "Singularity: Rethinking the Software Stack"

### Summary of major innovations （主要贡献）

使用C#(高级语言)以及少量的C和汇编实现了一款兼容一些新的设计理念的微操作系统——Singularity，在实现OS基本的功能基础上，实现了软件进程间的隔离、基于协议的频道通信与基于清单的系统属性安全性校验。

### What the problems the paper mentioned?（解决的主要问题）

1. 原始的操作系统设计模式无法保证程序员在为内核加入新的成分时不出现错误，这是由于编写内核的C语言并非内存安全的程序语言。
2. 在原来的设计模式下，如果要对程序源码进行安全性确认，进行确认的代码代价甚至远高于程序设计本身。
3. 即使在漏洞挖掘中发生了内核内存错误，由于程序并行性，漏洞可能难以复现，又由于内核程序的边界不明确，错误传播造成程序分析困难。

**综上所述**：Singularity使用内存安全的语言C#设计内核，并兼容轻量的安全验证机制，为系统运行时资源划分明确的边界。

### How about the important related works/papers?

* Sing# language 作为支持快速可靠消息交流的程序语言被设计用于Singularity
* 在对多核并行程序支持的处理上参考Chakraborty等人的意见，精心构造元数据的存储，支持不同进程自动分配到不同的处理器核
* 在汇编程序设计上，为了同时满足可验证安全和满足兼容性，结合了Bartok的工作，引入typed intermediate language，用于确保少部分用非安全编程语言编写的部分是安全的（诸如GC）。

### What are some intriguing aspects of the paper?

* todo

### How to test/compare/analyze the results?

文章没有关于OS的实验证明，但是提到Singularity的性能和兼容性可以与先前的优秀OS媲美，而如果要亲自实测，可以下载Singularity SDK测试benchmarks：<https://archive.codeplex.com/?p=singularity>



### How can the research be improved?

* todo

### If you write this paper, then how would you do?

和改善某方面研究的一小点不同，这篇Singularity介绍了一款全新的OS设计，比起罗列系统的新特性，更应该关注其设计思想以及在实现过程中如何克服困难——为什么别人没能用高级语言实现这个系统，而他们做到了，这中间做了怎么样的trade off。文章引入正确性检验正是弥补了小部分不得不用低级语言编程部分的安全性缺失缺陷

### Did you test the results by yourself? If so,What’s your test Results?

time consuming!

### Give the survey paper list in the same area of the paper your reading.





```
为何要这么设计？△
与其他设计相比，有何优缺点？△
对应用/硬件的适配情况如何？ 
通用性/专用性/目标有啥特点？
在现有的某些硬件架构下，或特定硬件下，这种os架构设计是否有适合的场景？
如何改进？ △
```

