# string 输入输出格式化总结

## 概括
1. 首先在程序开头处加上#include<map>以包含所需要的类文件map
还有一定要加上using namespace std;
如：map<string, string> map;
2. unordered_map和map相同，用法的区别就是，stl::map 的key需要定义operator< 。 而unordered_map需要定义hash_value函数并且重载operator==。对于内置类型，如string，这些都不用操心。对于自定义的类型做key，就需要自己重载operator< 或者hash_value()了。map红黑树有序，unordered_map无序hash值查找效率高。
//#include <unordered_map> c++11 才支持
3. map属于关联容器 如果支持c++11尽量用unorder_map,其内部使用hash实现查找效率更高。使用需要关联使用的。

## 增加 获取 删除 修改
总结： 
增加：使用 map[key]=value; 效果增加或存在替换
获取 map[key]; 效果得到value，或空，空对象（int->0,string "")
删除：指定元素要注意 删除后迭代器会失效。循环内不同于vector的erase返回下一个迭代器，返回void
所以循环内使用mapObj.erase(i++)备份迭代器。
修改： map[key]=value 


##参考
常用方法
https://www.cnblogs.com/xFreedom/archive/2011/05/16/2048037.html
string和stringStream介绍
http://blog.csdn.net/xw20084898/article/details/21939811