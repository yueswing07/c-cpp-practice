# vector 总结
## 概括
1. 首先在程序开头处加上#include<vector>以包含所需要的类文件vector
还有一定要加上using namespace std;
2. 内部红黑树实现，自动有序，不允许两个元素有相同的键值。

## 增加 获取 删除 修改
总结： 
增加：使用 .insert(val); 效果增加值，重复的值只存在一个。
获取 1.迭代器循环 2.find(val)找到返回迭代器，没有找到返回end迭代器位置
删除：指定元素要注意 删除后迭代器会失效。循环内不同于vector的erase返回下一个迭代器，返回void
所以循环内使用.erase(i++)备份迭代器。
修改： 不支持，可以使用先删除，后添加 

#include <set>
void setTest(){

	// create 
	set<string> setObj;
	setObj.insert("1");
	setObj.insert("2");
	setObj.insert("3");
	setObj.insert("4");


	// get 
	cout << "create get: ";
	for (auto i = setObj.begin(); i != setObj.end(); i++)
	{
		cout << (*i) << endl;
	}
	auto ret = setObj.find("3");
	if (ret != setObj.end())
	cout << "key get exist:" << *ret << endl;
	cout << "key get no exist:" << *ret << endl;
	ret = setObj.find("e");
	if (ret != setObj.end())
		cout << "key get exist:" << *ret << endl;
	cout << "key get no exist:" << "e" << endl;

	// delete
	auto count = setObj.erase("1");
	cout << "count = mapObj.erase(\"e\"):" << count << endl;
	count = setObj.erase("a");
	cout << "count = mapObj.erase(\"a\"):" << count << endl;
	// delete specified item
	for (auto i = setObj.begin(); i != setObj.end(); /*i++*/)
	{
		if ((*i) == "4")
		{
			setObj.erase(i++);
		}
		else
		{
			i++;
		}
	}
	cout << "delete specified item: ";
	for (auto i = setObj.begin(); i != setObj.end(); i++)
	{
		cout << (*i) << endl;
	}

	// update no exist

}
##参考

