# map总结
## 定义
1. 首先在程序开头处加上#include<map>以包含所需要的类文件map
还有一定要加上using namespace std;
如：map<string, string> map;
2. unordered_map和map相同，用法的区别就是，stl::map 的key需要定义operator< 。 而unordered_map需要定义hash_value函数并且重载operator==。对于内置类型，如string，这些都不用操心。对于自定义的类型做key，就需要自己重载operator< 或者hash_value()了。map红黑树有序，unordered_map无序hash值查找效率高。
#include <unordered_map> c++11 才支持

## 增加 获取 删除 修改
总结： 
增加：使用 map[key]=value; 效果增加或存在替换
获取 map[key]; 效果得到value，或空，空对象（int->0,string "")
删除：指定元素要注意 删除后迭代器会失效。循环内不同于vector的erase返回下一个迭代器，返回void
所以循环内使用mapObj.erase(i++)备份迭代器。
修改： map[key]=value 
#include <map>
void mapTest(){

	// create 
	map<string, string> mapObj;
	mapObj["a"] = "1";
	mapObj["b"] = "2";
	mapObj["c"] = "3";
	mapObj["d"] = "4";

	// get 
	cout << "create get: ";
	for (auto i = mapObj.begin(); i != mapObj.end(); i++)
	{
		cout << (*i).first << (*i).second << endl;
	}
	cout << "key get exist:" << mapObj["a"] << endl;

	cout << "key get no exist:" << mapObj["e"] << endl;

	auto iter = mapObj.find("b");
	if (iter != mapObj.end())
		cout << "Find, the value is " << iter->second << endl;
	else
		cout << "Do not Find" << endl;

	// delete
	auto count = mapObj.erase("e");
	cout << "count = mapObj.erase(\"e\"):" << count << endl;
	count = mapObj.erase("a");
	cout << "count = mapObj.erase(\"a\"):" << count << endl;
	// delete specified item
	for (auto i = mapObj.begin(); i != mapObj.end(); /*i++*/)
	{
		if (i->first == "c")
		{
			mapObj.erase(i++);
		}
		else
		{
			i++;
		}
	}
	cout << "delete specified item: ";
	for (auto i = mapObj.begin(); i != mapObj.end(); i++)
	{
		cout << (*i).first << (*i).second << endl;
	}

	// update
	cout << "update  item: ";
	mapObj["b"] = "b";
	for (auto i = mapObj.begin(); i != mapObj.end(); i++)
	{
		cout << (*i).first << (*i).second << endl;
	}

}

备注： 

最后，说，当不需要结果排好序时，最好用unordered_map。

## 理论
* map内部自建一颗红黑树，这颗树具有对数据自动排序的功能，所以在map内部所有的数据都是有序的。
* 特点是增加和删除节点对迭代器的影响很小，除了那个操作节点，对其他的节点都没有什么影响。
对于迭代器来说，可以修改实值，而不能修改key。

参考：
使用
https://www.cnblogs.com/fnlingnzb-learner/p/5833051.html
删除元素
http://blog.csdn.net/windren06/article/details/8141921
stl性能
http://blog.csdn.net/liu378606/article/details/20700655

