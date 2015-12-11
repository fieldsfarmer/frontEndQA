```java
//第一题，用的是Hashmap记录每个时间点已经储存的content
HashMap<String, HashMap<Integer, ArrayList<String>>>

//外面的HashMap的key是location
//里面HashMap的key是time
//ArrayList是某个时间点已经存入的content

//读一个content，如果是从时间1到3，那么在HashMap里key为1 2 3的时间都加入这个content
//如果有冲突就不put进去

//最重要的是code quality。 最好是clean code，简洁有效。数据结构选择合理。
//其次是算法高效或者creativity这种的。
//在code处于hire与no hire之间的时候，会看leadership， teamwork这种。
```
```java
//1. 我面试前看了一些面经，大概有一点概念，面试前一天自己用Java 模拟了一下类似于 OS round robin scheduling，练练手。
//2. 熟悉一下自己想用的语言的read in file, write out file.其实他们都会提供代码handle这部分，但是熟悉一下，还是有好处。
//3. 你所有的code,其实只在一个file里面完成，我一开始是在main里面写，也能跑，后来还是被印度小哥提醒，发现原来在另外一个file里面，comment还写着 // implement your code here. 
//4. 给你的input file很大，可以自己截取最开始的10个entry左右，用小的file 测试代码。
//5. 关于选题，说实话我只看懂了一个，另外两个一开始没有很快有思路。这个时候，一定要speak for yourself, 不要表现得很急，但是也绝不要礼让，想做哪个，就一定要说出来。我可能是占了作为女生的便宜，组里的白人大叔让我先选了，感觉那个印度小哥也很想做这个。 
//6. 选完了题目，就赶紧想思路，赶紧写，数据结构很重要，没有什么算法。而数据结果，无非也就是hashmap, set, arraylist几个，能简单的，不要往 tree 什么的去想。
//hashmap, hashmap, hashmap, 重要的东西说三遍。

//7. 一定写comment, 讲清楚你的approach。我还写了Java doc。 README没有时间写了，也没有写unit test, 看来这都不是问题，有时间写写，没时间还是保证保证代码。. from: 1point3acres.com/bbs 
//8. 尽量分成小的method/function写，注意命名，总之代码保持简洁，方便自己写，也方便他们事后读。
//9. 第一次30分钟面试的时候，不一定要完全都想通，保持一种与面试官讨论，向面试官学习的心态，把自己的想法有条有理讲清楚，把自己隐约想到，但是还没完全想好怎么做的，也要讲出来，面试官会帮助你理清思路。
//10. 个人觉得team work, leadership 没什么大用，也体现不了太多，但是在自己有时间的情况下，尽量帮队友，有时候，可能就是一个很小的地方，当局者迷，你可能一下子就看出来了，他还卡在那里。这样反过来，他们也会帮助你。
//11. 西雅图在我去的时候阳光灿烂，我已经是爱上那里了，大家面完之后，一定去海边逛逛，尝尝当地的chowder. 一天65刀饭钱，我是完全用不掉啊。
```
```java
我做的第二部分。 第一次面试官谈话的时候我几已经写完了，可以运行。 这里面试官主要想看有两点。
一是你存储输入数据用的数据结构， 
二是你解决问题用的算法。我的做法基本上就是面试官要的了,  结果就是面试官没什么可说的了。 于是就只好谈了下为什么没用greedy。
```