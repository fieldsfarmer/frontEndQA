```java
//第一题，用的是Hashmap记录每个时间点已经储存的content
HashMap<String, HashMap<Integer, ArrayList<String>>>

//外面的HashMap的key是location
//里面HashMap的key是time
//ArrayList是某个时间点已经存入的content

//读一个content，如果是从时间1到3，那么在HashMap里key为1 2 3的时间都加入这个content
//如果有冲突就不put进去
```