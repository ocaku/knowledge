cityhash系列字符串散列算法是由著名的搜索引擎公司Google 发布的 (http://www.cityhash.org.uk/)。

Google发布的有两种算法：cityhash64 与 cityhash128。它们分别根据字串计算 64 和 128 位的散列值。这些算法不适用于加密，但适合用在散列表等处。

目前cityHash算法只有C++的实现,就性能而言，CityHash性能略胜MurmurHash算法。有兴趣的同学可以到http://www.cityhash.org.uk/index.php去看看。

### Google发布CityHash系列散列算法 
Google发布了 CityHash系列字符串散列算法。今天发布的有两种算法：CityHash64 与 CityHash128。它们分别根据字串计算64和128位的散列值。这些算法不适用于加密，但适合用在散列表等处。

Google一直在根据其数据中心常用的CPU对算法进行优化，结果发现对大多数个人计算机与笔记本同样有效益。尤其是在64位寄存器、指令集级的并行，以及快速非对其内存存取方面。

该算法的开发受到了前人在散列算法方面的巨大启发，尤其是Austin Appleby的MurmurHash。但CityHash的主要优点是大部分步骤包含了至少两步独立的数学运算。现代CPU通常能从这种代码获得最佳性能。

但CityHash也有其缺点：代码较同类流行算法复杂。Google希望为速度而不是为了简单而优化，因此没有照顾较短输入的特例。

总体而言，CityHash64与CityHash128是解决经典问题的全新算法。在实际应用中，Google预计CityHash64在速度方面至少能提高 30%，并有望提高多达两倍。此外，这些算法的统计特性也很完备。
