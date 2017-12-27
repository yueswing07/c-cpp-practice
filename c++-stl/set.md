# vector 总结
## 定义
1. 首先在程序开头处加上#include<vector>以包含所需要的类文件vector
还有一定要加上using namespace std;


## 增加 获取 删除 修改
总结： 
增加：使用 .insert(val); 效果增加值，重复的值只存在一个。
获取 map[key]; 效果得到value，或空，空对象（int->0,string "")
删除：指定元素要注意 删除后迭代器会失效。循环内不同于vector的erase返回下一个迭代器，返回void
所以循环内使用mapObj.erase(i++)备份迭代器。
修改： map[key]=value 

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

