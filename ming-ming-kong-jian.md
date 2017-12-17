# 命名空间 
c++ 命名空间
## 1. 定义
// 文件 A.h
namespace A {
    int a;
    namespace A1 { // 嵌套定义
    }
}
## 2. 使用
#include <A.h>
use namespace A; // 引入整体
use namespace A.a // 引入单体
## 3. 命名空间重名
namespace B = A; // A取别名为B
## 4. 常见使用
using namespace std;  // 标准库函数库
## 5. 常见规则和问题
类名和命名空间名称不要相同