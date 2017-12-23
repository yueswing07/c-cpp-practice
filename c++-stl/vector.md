# vector 总结
## 定义
1. 首先在程序开头处加上#include<vector>以包含所需要的类文件vector
还有一定要加上using namespace std;


## 增加 获取 删除 修改

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

