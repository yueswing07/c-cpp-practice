# vector 总结
## 定义
1. 首先在程序开头处加上#include<vector>以包含所需要的类文件vector
还有一定要加上using namespace std;


## 增加 获取 删除 修改
总结： 删除指定元素要注意 删除后迭代器会失效。采用两种方式解决：1.删除元素后，让迭代器重头开始。2.erase 返回下一元素的迭代器给迭代器，增加i == vectorStr.end() 跳出循环判断。
#include <vector>
void vectorTest(){
	// create 
	vector<string> vectorStr;
	vectorStr.push_back("a");
	vectorStr.push_back("a");
	vectorStr.push_back("a");
	vectorStr.push_back("b");
	vectorStr.push_back("c");

	// get 
	cout << "create get: ";
	for (auto i = vectorStr.begin(); i < vectorStr.end(); i++)
	{
		cout << (*i) << endl;
	}

	// delete
	vectorStr.pop_back(); // delete first
	cout << "delete first: ";
	for (auto i = vectorStr.begin(); i < vectorStr.end(); i++)
	{
		cout << (*i) << endl;
	}
	// delete specified item
	for (auto i = vectorStr.begin(); i < vectorStr.end(); i++)
	{ 
		if ((*i) == "b"){
			vectorStr.erase(i);
			i = vectorStr.begin();
		}
	}
	for (auto i = vectorStr.begin(); i < vectorStr.end(); i++)
	{
		if ((*i) == "b"){
			i = vectorStr.erase(i);
			//i = vectorStr.begin();
		}
		if (i == vectorStr.end()){
			break;
		}
	}
	cout << "delete specified item: ";
	for (auto i = vectorStr.begin(); i < vectorStr.end(); i++)
	{
		cout << (*i) << endl;
	}

	// update
	cout << "delete specified item: ";
	vectorStr[0] = "0";
	for (auto i = vectorStr.begin(); i < vectorStr.end(); i++)
	{
		cout << (*i) << endl;
	}
	vectorStr.at(1) = "1";
	for (auto i = vectorStr.begin(); i < vectorStr.end(); i++)
	{
		cout << (*i) << endl;
	}

	for (auto i = vectorStr.begin(); i < vectorStr.end(); i++)
	{
		if ((*i) == "c"){
			*i = "d";
		}
	}
	for (auto i = vectorStr.begin(); i < vectorStr.end(); i++)
	{
		cout << (*i) << endl;
	}


}

##参考
删除：http://blog.csdn.net/duan19920101/article/details/50717748
http://blog.csdn.net/hancunai0017/article/details/7032383

