# C-p27-VS-
C语言学习笔记 p27VS环境及测试
#include<stdio.h>
//断点的作用：在设置断点的那一行停止运行代码
//栈区：默认先使用高低之空间，再使用低地址空间
//数组随着下标的增长地址是由低到高变化的
void my_strcpy(char* dest,char* src)
{
    while()
    {
      *dest++ = *src++;
    }
    //拷贝\0
    *dest=*src;
}
//优化my_strcpy
void my_strcpy(char* dest,char* src)
{
    while(*dest++=*scr++)
    {
        ;
    }
}
//比上面一种方法效率高
void my_strcpy(char* dest,char* src)
{
   assert(dest!=NULL);//断言
   assert(src!=NULL);//断言
        while(*dest++=*scr++)
        {
            ;
        }
}
//比上一种方法效率高
char*  my_strcpy(char* dest,const char* src)
{
    char* ret=dest;
    assert(dest!=NULL);//断言
    assert(src!=NULL);//断言
    //把src指向的字符串拷贝到dest指向的2空间，包括'\0'字符
    while(*dest++=*scr++)
    {
        ;
    }
    return ret;
}
int main()
{
    //strcpy字符串拷贝
    char arr1[]="########################";
    char arr2[]="bit";
    my_strcpy(arr1,arr2);//先放拷贝的目的地，再放拷贝的源头
    printf("%s\n",arr1);
    return 0;
}

int main()
{
    const int num=10;

    const int* p=&num;//注：这里还有int* const p,这个是修饰p的但是*p是可以被改变的
    *p=20;//const放在指针变量的*左边，修饰的是*p，也就是说：不能通过p来改变*p(num)的值
    //const放在指针变量的*右边，修饰的是指针变量p本身，也就是说：p不能被改变了
    int n=100;
    p=&n;
    printf("%d\n",num);
    return 0;
}



//完美strlen代码
my_strlen(const char* str)
{
    int count=0;
    assert(str!=NULL);//保证指针的有效性，增强健壮性
    while(*str!='\0')
    {
        count++;
        str++;
    }
    return count;
}
int main()
{
    char arr[]="abcdef";
    my_STRLEN(ARR);
    PRINTF("%d\n",len);
    return 0;
}



//编译型错误：在编译过程中查出来的语法错误，一般都很容易找到
//链接型错误：
int main()
{
    int a=10;
    int b=20;
    int sum=Add(a,b);
    printf("%d\n",sum);//这里没有定义Add则会出现链接型错误，一般出现这种错误都是大小写错误
    return 0;
}
//运行时错误
//借助调试来搞，一般这种错误最难搞
