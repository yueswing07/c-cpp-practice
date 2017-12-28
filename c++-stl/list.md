# map总结
## 概括
1. 首先在程序开头处加上#include<map>以包含所需要的类文件map
还有一定要加上using namespace std;
如：map<string, string> map;
2. unordered_map和map相同，用法的区别就是，stl::map 的key需要定义operator< 。 而unordered_map需要定义hash_value函数并且重载operator==。对于内置类型，如string，这些都不用操心。对于自定义的类型做key，就需要自己重载operator< 或者hash_value()了。map红黑树有序，unordered_map无序hash值查找效率高。
//#include <unordered_map> c++11 才支持
3. map属于关联容器 如果支持c++11尽量用unorder_map,其内部使用hash实现查找效率更高。使用需要关联使用的。

## 增加 获取 删除 修改
总结： 
增加：push_back push_front 添加 可以有重复元素
获取; front back 头尾元素获取  
删除：1.指定元素 erease, pop_front pop_back 头尾删除
修改： 支持循环找到指定元素 复制替换
#include <list>
void listTest(){
	// create
	list<string> listObj;
	listObj.push_back("b");
	listObj.push_back("c");
	listObj.push_back("a");
	listObj.push_front("d");
	listObj.push_front("d");
	listObj.push_front("d");

	// get  
	for (auto i = listObj.begin(); i != listObj.end(); i++){
		cout << (*i);
	}
	cout << endl;
	cout << "get first item: " << listObj.front() << endl;
	cout << "get last item: " << listObj.back() << endl;

	// delete 
	listObj.pop_front();
	cout << "delete first item" << endl;
	for (auto i = listObj.begin(); i != listObj.end(); i++){
		cout << (*i);
	}
	cout << endl;
	listObj.pop_back();
	cout << "delete first item" << endl;
	for (auto i = listObj.begin(); i != listObj.end(); i++){
		cout << (*i);
	}
	cout << endl;

	//update 
	for (auto i = listObj.begin(); i != listObj.end(); i++){
		if ((*i) == "c"){
			(*i) = "e";
		}
	}
	cout << "update item" << endl;
	for (auto i = listObj.begin(); i != listObj.end(); i++){
		cout << (*i);
	}
	cout << endl;

}

备注： 


## 理论
* 双向列表适合两端操作

参考：

