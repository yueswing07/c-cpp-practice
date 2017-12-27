# string 输入输出格式化总结

## 概括
1. 首先在程序开头处加上#include<string>以包含所需要的类文件string
还有一定要加上using namespace std;
如：string str;
2.
3. 

## 增加 获取 删除 修改
总结： 
增加：使用 str = "aaa"; 效果增加或存在替换 直接复制也可以替换
获取： 获取c风格字符 str.c_str()
删除：erase replace 等
修改： 1.复制语句 2.replace
#include <string>
void strTest(){

	// create
	char *cStr = "abcdef";
	string str1 = "1234567";
	string str2(cStr);
	cout << str1 << endl;
	cout << str2 << endl;

	// 获取
	//[]均返回当前字符串中第n个字符的位置，但at函数提供范围检查，当越界时会抛出out_of_range异常，下标运算符[]不提供检查访问。
	cout << str1[0] << str1.at(1) << endl; 
	cout << "c style string" << str1.c_str() << endl;
	cout << str1.find("3") << str1.find("45") << str1.rfind("56") << endl;
	cout << "find fail " << str1.find("a") << endl;

	//delete 
	cout << str1.erase(0, 2) << endl;

	//update
	str1 = "000";
	cout << str1 << endl;
	cout << str2.insert(0, "12") << endl;
	cout << str2.replace(0, 2, "0000");
	

}

##参考
常用方法
https://www.cnblogs.com/xFreedom/archive/2011/05/16/2048037.html
string和stringStream介绍
http://blog.csdn.net/xw20084898/article/details/21939811