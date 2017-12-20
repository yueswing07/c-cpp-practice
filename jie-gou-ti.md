# 结构体

## 结构体读写 不要存复杂类型
结构体数据写入存储空间（文件，内存空间等），在读写时，结构体成员要用基础数据类型
typedef struct {
    char name[128];
    string strName;
    int processId;
} AppInfo;
写结构体 读接头体
pBuffer 为 void* 指针
写：memcpy( pBuffer, (const char *)&appInfo, sizeof(appInfo) );
读：memcpy( (void*)(&appInfo), pBuffer, sizeof(appInfo) );
备注：appInfo 结构体需要为基础数据
当我 在appInfo 中使用string类型时 出现了错误。