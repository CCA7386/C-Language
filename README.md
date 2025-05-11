# C-Language
# 超详细C语言讲解 - 逐行注释分析

## 1. Hello World 程序详解

```c
/* 
 * 预处理指令：包含标准输入输出头文件
 * #include 是包含指令
 * <stdio.h> 是标准输入输出库头文件
 * 作用：提供printf()等输入输出函数的声明
 */
#include <stdio.h>

/*
 * main函数：程序的入口点
 * int 表示函数返回整数类型
 * main 是函数名
 * () 表示无参数
 * {} 包含函数体
 * 作用：程序从这里开始执行
 */
int main() {
    /*
     * printf函数：格式化输出函数
     * "Hello, World!\n" 是要输出的字符串
     * \n 是换行符，将光标移动到下一行开头
     * ; 表示语句结束
     * 作用：在屏幕上显示"Hello, World!"并换行
     */
    printf("Hello, World!\n");
    
    /*
     * return语句：结束函数并返回值
     * 0 表示程序正常退出
     * 非0值通常表示错误代码
     * 作用：告诉操作系统程序执行成功
     */
    return 0;
}
```

## 2. 变量与数据类型详解

```c
#include <stdio.h>

int main() {
    /*
     * 变量声明：分配内存空间
     * int 表示整数类型(4字节)
     * age 是变量名(标识符)
     * 作用：创建一个可以存储整数的变量
     */
    int age;
    
    /*
     * 变量赋值：将值存入变量
     * = 是赋值运算符
     * 25 是整数字面量
     * 作用：将25存储到age变量中
     */
    age = 25;
    
    /*
     * 变量声明并初始化
     * float 表示单精度浮点类型(4字节)
     * height 是变量名
     * 1.75f 是浮点数字面量(f表示float)
     * 作用：创建并初始化一个浮点变量
     */
    float height = 1.75f;
    
    /*
     * 字符变量
     * char 表示字符类型(1字节)
     * initial 是变量名
     * 'J' 是字符字面量(单引号)
     * 作用：存储单个ASCII字符
     */
    char initial = 'J';
    
    /*
     * 格式化输出
     * %d 表示整数占位符
     * %f 表示浮点数占位符
     * %c 表示字符占位符
     * \t 是制表符(8个空格)
     * 作用：按格式输出变量值
     */
    printf("Age: %d\tHeight: %.2f\tInitial: %c\n", age, height, initial);
    
    return 0;
}
```

## 3. 运算符详解

```c
#include <stdio.h>

int main() {
    /*
     * 算术运算符示例
     * + 加法
     * - 减法
     * * 乘法
     * / 除法
     * % 取模(余数)
     */
    int a = 10, b = 3;
    printf("a + b = %d\n", a + b);  // 13
    printf("a - b = %d\n", a - b);  // 7
    printf("a * b = %d\n", a * b);  // 30
    printf("a / b = %d\n", a / b);  // 3 (整数除法)
    printf("a %% b = %d\n", a % b); // 1 (余数)
    
    /*
     * 自增/自减运算符
     * ++ 自增1
     * -- 自减1
     * 前缀形式(++a): 先增减后使用
     * 后缀形式(a++): 先使用后增减
     */
    int c = 5;
    printf("c++ = %d\n", c++); // 输出5，然后c变为6
    printf("++c = %d\n", ++c); // c先变为7，然后输出7
    
    /*
     * 关系运算符
     * == 等于
     * != 不等于
     * >  大于
     * <  小于
     * >= 大于等于
     * <= 小于等于
     * 返回1(真)或0(假)
     */
    printf("a == b: %d\n", a == b); // 0
    printf("a > b: %d\n", a > b);   // 1
    
    /*
     * 逻辑运算符
     * && 逻辑与(两个条件都为真)
     * || 逻辑或(任一条件为真)
     * !  逻辑非(反转条件)
     */
    int x = 1, y = 0;
    printf("x && y: %d\n", x && y); // 0
    printf("x || y: %d\n", x || y); // 1
    printf("!x: %d\n", !x);         // 0
    
    /*
     * 位运算符(操作二进制位)
     * &  按位与
     * |  按位或
     * ^  按位异或
     * ~  按位取反
     * << 左移
     * >> 右移
     */
    unsigned int m = 0b1100, n = 0b1010;
    printf("m & n: %u\n", m & n); // 0b1000 (8)
    printf("m | n: %u\n", m | n); // 0b1110 (14)
    printf("m ^ n: %u\n", m ^ n); // 0b0110 (6)
    printf("~m: %u\n", ~m);       // 取决于系统位数
    printf("m << 2: %u\n", m << 2); // 0b110000 (48)
    printf("m >> 1: %u\n", m >> 1); // 0b0110 (6)
    
    return 0;
}
```

## 4. 控制结构详解

### if-else语句

```c
#include <stdio.h>

int main() {
    int score = 85;
    
    /*
     * if条件语句
     * if 关键字开始条件判断
     * (score >= 90) 是条件表达式
     * {} 包含条件为真时执行的代码块
     * else if 提供额外条件检查
     * else 处理所有其他情况
     */
    if (score >= 90) {
        printf("Grade: A\n");
    } 
    else if (score >= 80) {  // 80 <= score < 90
        printf("Grade: B\n");
    } 
    else if (score >= 70) {  // 70 <= score < 80
        printf("Grade: C\n");
    } 
    else {                   // score < 70
        printf("Grade: D\n");
    }
    
    /*
     * 三元条件运算符
     * 语法：条件 ? 表达式1 : 表达式2
     * 如果条件为真，返回表达式1，否则返回表达式2
     */
    char *result = (score >= 60) ? "Pass" : "Fail";
    printf("Result: %s\n", result);
    
    return 0;
}
```

### switch语句

```c
#include <stdio.h>

int main() {
    char grade = 'B';
    
    /*
     * switch多分支语句
     * switch(expression) 根据表达式值跳转
     * case 'A': 匹配特定值的情况
     * break: 跳出switch块
     * default: 所有情况不匹配时执行
     */
    switch (grade) {
        case 'A':  // 如果grade == 'A'
            printf("Excellent!\n");
            break;  // 必须break，否则会继续执行下一个case
        case 'B':  // 如果grade == 'B'
            printf("Good job!\n");
            break;
        case 'C':  // 如果grade == 'C'
            printf("You passed\n");
            break;
        case 'D':  // 如果grade == 'D'
            printf("Better try again\n");
            break;
        default:   // 如果grade不匹配任何case
            printf("Invalid grade\n");
    }
    
    return 0;
}
```

### 循环结构

```c
#include <stdio.h>

int main() {
    /*
     * while循环
     * 先检查条件，条件为真时执行循环体
     * 适合不确定循环次数的情况
     */
    int i = 0;
    printf("while loop:\n");
    while (i < 5) {  // 条件检查
        printf("%d ", i);
        i++;        // 改变循环变量
    }
    printf("\n");
    
    /*
     * do-while循环
     * 先执行循环体，再检查条件
     * 至少执行一次循环体
     */
    int j = 0;
    printf("do-while loop:\n");
    do {
        printf("%d ", j);
        j++;
    } while (j < 5);  // 条件检查在末尾
    printf("\n");
    
    /*
     * for循环
     * 初始化; 条件; 增量 三个部分
     * 适合已知循环次数的情况
     */
    printf("for loop:\n");
    for (int k = 0; k < 5; k++) {  // k=0初始化; k<5条件; k++增量
        printf("%d ", k);
    }
    printf("\n");
    
    /*
     * 循环控制语句
     * break: 立即终止整个循环
     * continue: 跳过当前迭代，继续下一次循环
     */
    printf("Loop with break and continue:\n");
    for (int n = 0; n < 10; n++) {
        if (n == 2) continue;  // 跳过n=2的迭代
        if (n == 7) break;     // n=7时终止循环
        printf("%d ", n);
    }
    printf("\n");
    
    return 0;
}
```

## 5. 函数详解

```c
#include <stdio.h>

/*
 * 函数声明(原型)
 * 告诉编译器函数的存在
 * int 是返回类型
 * add 是函数名
 * (int a, int b) 是参数列表
 * ; 表示声明结束
 */
int add(int a, int b);

/*
 * 主函数
 */
int main() {
    int num1 = 5, num2 = 3;
    
    /*
     * 函数调用
     * add(num1, num2) 调用add函数
     * 传递num1和num2的值作为参数
     * 返回值可以直接使用或赋给变量
     */
    int sum = add(num1, num2);
    printf("%d + %d = %d\n", num1, num2, sum);
    
    return 0;
}

/*
 * 函数定义
 * 实现函数的具体功能
 * int 表示返回整数
 * add 是函数名
 * int a, int b 是形式参数
 * {} 包含函数体
 * return 返回计算结果
 */
int add(int a, int b) {
    /*
     * 局部变量
     * 只在函数内部可见
     */
    int result = a + b;
    
    /*
     * return语句
     * 返回计算结果给调用者
     * 结束函数执行
     */
    return result;
}
```

## 6. 数组详解

```c
#include <stdio.h>

int main() {
    /*
     * 一维数组声明和初始化
     * int 表示数组元素类型
     * numbers 是数组名
     * [5] 表示数组大小(5个元素)
     * {...} 初始化数组元素
     * 下标从0开始
     */
    int numbers[5] = {10, 20, 30, 40, 50};
    
    /*
     * 访问数组元素
     * numbers[0] 第一个元素
     * numbers[4] 最后一个元素
     */
    printf("First element: %d\n", numbers[0]);
    printf("Third element: %d\n", numbers[2]);
    
    /*
     * 修改数组元素
     * numbers[1] = 99 修改第二个元素
     */
    numbers[1] = 99;
    printf("Modified second element: %d\n", numbers[1]);
    
    /*
     * 遍历数组
     * sizeof(numbers) 返回数组总字节数
     * sizeof(numbers[0]) 返回单个元素字节数
     * 相除得到元素个数
     */
    int length = sizeof(numbers) / sizeof(numbers[0]);
    printf("Array elements: ");
    for (int i = 0; i < length; i++) {
        printf("%d ", numbers[i]);
    }
    printf("\n");
    
    /*
     * 二维数组(矩阵)
     * 3行2列的数组
     * 第一个下标是行，第二个是列
     */
    int matrix[3][2] = {
        {1, 2},  // 第一行
        {3, 4},  // 第二行
        {5, 6}   // 第三行
    };
    
    /*
     * 访问二维数组元素
     * matrix[row][col]
     */
    printf("Matrix[1][1]: %d\n", matrix[1][1]);  // 4
    
    /*
     * 遍历二维数组
     * 外层循环处理行
     * 内层循环处理列
     */
    printf("Matrix elements:\n");
    for (int row = 0; row < 3; row++) {
        for (int col = 0; col < 2; col++) {
            printf("%d ", matrix[row][col]);
        }
        printf("\n");  // 每行结束后换行
    }
    
    return 0;
}
```

## 7. 指针详解

```c
#include <stdio.h>

int main() {
    /*
     * 指针基础
     * & 取地址运算符
     * * 解引用运算符
     */
    int var = 42;       // 普通整型变量
    int *ptr = &var;    // 指针变量，存储var的地址
    
    /*
     * 打印变量值和地址
     * %p 格式化输出指针(地址)
     */
    printf("var的值: %d\n", var);          // 42
    printf("var的地址: %p\n", &var);       // 如0x7ffd5fbff8ac
    printf("ptr存储的地址: %p\n", ptr);    // 同上
    printf("*ptr的值: %d\n", *ptr);        // 42
    
    /*
     * 通过指针修改变量值
     * *ptr = 100 解引用并赋值
     */
    *ptr = 100;
    printf("修改后var的值: %d\n", var);    // 100
    
    /*
     * 指针算术
     * 指针加减整数根据指向类型大小移动
     */
    int arr[] = {10, 20, 30, 40, 50};
    int *arr_ptr = arr;  // 指向数组第一个元素
    
    printf("arr_ptr指向: %d\n", *arr_ptr);      // 10
    arr_ptr++;           // 移动到下一个int位置(通常4字节)
    printf("arr_ptr现在指向: %d\n", *arr_ptr);  // 20
    arr_ptr += 2;        // 向前移动两个int
    printf("arr_ptr现在指向: %d\n", *arr_ptr);  // 40
    
    /*
     * 指针与数组的关系
     * 数组名可以看作指向第一个元素的指针
     */
    printf("arr[3] = %d\n", arr[3]);          // 40
    printf("*(arr + 3) = %d\n", *(arr + 3));  // 40
    
    /*
     * 指针数组
     * 数组元素是指针
     */
    int x = 5, y = 10, z = 15;
    int *ptr_arr[3] = {&x, &y, &z};  // 存储三个指针
    
    for (int i = 0; i < 3; i++) {
        printf("ptr_arr[%d] = %p, *ptr_arr[%d] = %d\n", 
               i, ptr_arr[i], i, *ptr_arr[i]);
    }
    
    /*
     * 指向指针的指针
     */
    int value = 255;
    int *p = &value;
    int **pp = &p;  // 指向指针的指针
    
    printf("value = %d\n", value);  // 255
    printf("*p = %d\n", *p);        // 255
    printf("**pp = %d\n", **pp);    // 255
    
    return 0;
}
```

## 8. 结构体详解

```c
#include <stdio.h>
#include <string.h>

/*
 * 定义结构体类型
 * struct 关键字
 * Student 是结构体标签
 * {} 内是成员列表
 * ; 结束定义
 */
struct Student {
    char name[50];    // 字符数组成员
    int age;          // 整型成员
    float gpa;        // 浮点型成员
};  // 注意分号不能少

int main() {
    /*
     * 声明结构体变量
     * struct Student 是类型
     * student1 是变量名
     */
    struct Student student1;
    
    /*
     * 访问结构体成员
     * . 成员运算符
     * strcpy 复制字符串
     */
    strcpy(student1.name, "Alice");
    student1.age = 20;
    student1.gpa = 3.8f;
    
    /*
     * 结构体初始化
     * 可以在声明时初始化
     */
    struct Student student2 = {"Bob", 21, 3.5f};
    
    /*
     * 打印结构体成员
     */
    printf("Student1: %s, %d, %.2f\n", 
           student1.name, student1.age, student1.gpa);
    printf("Student2: %s, %d, %.2f\n", 
           student2.name, student2.age, student2.gpa);
    
    /*
     * 结构体指针
     * -> 箭头运算符访问指针指向的结构体成员
     */
    struct Student *ptr = &student1;
    printf("Pointer access: %s\n", ptr->name);  // Alice
    
    /*
     * 结构体数组
     */
    struct Student class[3] = {
        {"Charlie", 22, 3.2f},
        {"David", 20, 3.9f},
        {"Eve", 21, 3.7f}
    };
    
    /*
     * 遍历结构体数组
     */
    printf("Class list:\n");
    for (int i = 0; i < 3; i++) {
        printf("%s\t%d\t%.2f\n", 
               class[i].name, class[i].age, class[i].gpa);
    }
    
    /*
     * 结构体大小
     * sizeof 运算符计算字节数
     */
    printf("Size of Student: %lu bytes\n", sizeof(struct Student));
    
    return 0;
}
```
# C语言全面讲解（续）

## 十九、文件操作深入详解

### 1. 文本文件与二进制文件操作

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    /* 
     * 文本文件写入操作
     * fopen() 打开文件
     * 参数1: 文件名
     * 参数2: 打开模式
     *   "w" - 写入(覆盖)
     *   "a" - 追加
     *   "r" - 读取
     *   "w+" - 读写(覆盖)
     *   "a+" - 读写(追加)
     * 返回: FILE指针
     */
    FILE *textFile = fopen("example.txt", "w");
    
    if (textFile == NULL) {  // 检查文件是否成功打开
        printf("无法打开文件!\n");
        exit(1);  // 异常退出程序
    }
    
    /* 
     * fprintf() 格式化写入文件
     * 类似printf，但第一个参数是文件指针
     */
    fprintf(textFile, "这是一行文本\n");
    fprintf(textFile, "数字: %d, 浮点数: %.2f\n", 42, 3.14159);
    
    fclose(textFile);  // 关闭文件，释放资源

    /* 
     * 文本文件读取操作
     */
    textFile = fopen("example.txt", "r");
    if (textFile == NULL) {
        printf("无法打开文件!\n");
        exit(1);
    }
    
    char buffer[255];  // 缓冲区存储读取的内容
    
    /* 
     * fgets() 逐行读取文件
     * 参数1: 存储缓冲区
     * 参数2: 缓冲区大小
     * 参数3: 文件指针
     * 返回: 读取的字符串或NULL(文件结束)
     */
    while (fgets(buffer, 255, textFile) != NULL) {
        printf("%s", buffer);
    }
    
    fclose(textFile);

    /* 
     * 二进制文件操作
     * "wb" - 二进制写入
     * "rb" - 二进制读取
     */
    FILE *binFile = fopen("data.bin", "wb");
    if (binFile == NULL) {
        printf("无法创建二进制文件!\n");
        exit(1);
    }
    
    int data[] = {10, 20, 30, 40, 50};
    
    /* 
     * fwrite() 二进制写入
     * 参数1: 数据指针
     * 参数2: 每个元素大小
     * 参数3: 元素数量
     * 参数4: 文件指针
     * 返回: 成功写入的元素数量
     */
    size_t written = fwrite(data, sizeof(int), 5, binFile);
    printf("成功写入 %zu 个整数\n", written);
    
    fclose(binFile);

    /* 
     * 二进制文件读取
     */
    binFile = fopen("data.bin", "rb");
    if (binFile == NULL) {
        printf("无法打开二进制文件!\n");
        exit(1);
    }
    
    int readData[5];
    
    /* 
     * fread() 二进制读取
     * 参数类似fwrite
     */
    size_t read = fread(readData, sizeof(int), 5, binFile);
    printf("成功读取 %zu 个整数:\n", read);
    for (int i = 0; i < 5; i++) {
        printf("%d ", readData[i]);
    }
    printf("\n");
    
    fclose(binFile);

    return 0;
}
```

### 2. 文件定位函数详解

```c
#include <stdio.h>

int main() {
    FILE *file = fopen("seek.txt", "w+");
    if (file == NULL) {
        printf("无法打开文件!\n");
        return 1;
    }
    
    fprintf(file, "0123456789ABCDEFGHIJ");  // 写入20个字符
    
    /* 
     * fseek() 文件定位
     * 参数1: 文件指针
     * 参数2: 偏移量
     * 参数3: 起始位置
     *   SEEK_SET - 文件开头
     *   SEEK_CUR - 当前位置
     *   SEEK_END - 文件末尾
     */
    fseek(file, 5, SEEK_SET);  // 移动到第5个字节(从0开始)
    
    char ch = fgetc(file);  // 读取当前字符
    printf("第5个字符: %c\n", ch);  // '5'
    
    /* 
     * ftell() 获取当前文件位置
     * 返回: 当前位置(字节偏移量)
     */
    long position = ftell(file);
    printf("当前位置: %ld\n", position);  // 6(因为读取后位置前进)
    
    fseek(file, -3, SEEK_CUR);  // 从当前位置后退3字节
    position = ftell(file);
    printf("后退后的位置: %ld\n", position);  // 3
    
    /* 
     * rewind() 重置文件位置到开头
     */
    rewind(file);
    position = ftell(file);
    printf("重置后的位置: %ld\n", position);  // 0
    
    fclose(file);
    return 0;
}
```

## 二十、动态内存管理深入

### 1. 内存分配函数对比

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    /* 
     * malloc() 分配内存
     * 参数: 需要分配的字节数
     * 返回: 指向分配内存的void指针
     * 注意: 分配的内存未初始化
     */
    int *mallocPtr = (int *)malloc(5 * sizeof(int));
    if (mallocPtr == NULL) {
        printf("内存分配失败!\n");
        return 1;
    }
    
    printf("malloc分配的内存内容(未初始化):\n");
    for (int i = 0; i < 5; i++) {
        printf("%d ", mallocPtr[i]);  // 内容不确定
    }
    printf("\n");
    
    /* 
     * calloc() 分配并初始化内存
     * 参数1: 元素数量
     * 参数2: 每个元素大小
     * 返回: 指向分配内存的void指针
     * 注意: 分配的内存初始化为0
     */
    int *callocPtr = (int *)calloc(5, sizeof(int));
    if (callocPtr == NULL) {
        printf("内存分配失败!\n");
        free(mallocPtr);  // 释放之前分配的内存
        return 1;
    }
    
    printf("calloc分配的内存内容(初始化为0):\n");
    for (int i = 0; i < 5; i++) {
        printf("%d ", callocPtr[i]);  // 全为0
    }
    printf("\n");
    
    /* 
     * realloc() 重新分配内存
     * 参数1: 原内存指针
     * 参数2: 新的大小
     * 返回: 指向新内存的指针
     * 注意: 新内存可能移动位置
     */
    int *reallocPtr = (int *)realloc(mallocPtr, 10 * sizeof(int));
    if (reallocPtr == NULL) {
        printf("内存重新分配失败!\n");
        free(mallocPtr);
        free(callocPtr);
        return 1;
    }
    
    printf("realloc后的内存地址: %p (原地址: %p)\n", 
           (void *)reallocPtr, (void *)mallocPtr);
    
    // 使用新内存
    for (int i = 0; i < 10; i++) {
        reallocPtr[i] = i * 2;
    }
    
    /* 
     * free() 释放内存
     * 参数: 需要释放的内存指针
     * 注意: 只能释放malloc/calloc/realloc分配的内存
     */
    free(reallocPtr);
    free(callocPtr);
    
    /* 
     * 动态分配字符串
     */
    char *str = (char *)malloc(50 * sizeof(char));
    if (str == NULL) {
        printf("内存分配失败!\n");
        return 1;
    }
    
    strcpy(str, "这是一个动态分配的字符串");
    printf("%s\n", str);
    
    // 调整字符串大小
    char *newStr = (char *)realloc(str, 100 * sizeof(char));
    if (newStr == NULL) {
        printf("内存重新分配失败!\n");
        free(str);
        return 1;
    }
    
    strcat(newStr, " - 现在它有更多空间了!");
    printf("%s\n", newStr);
    
    free(newStr);
    
    return 0;
}
```

### 2. 常见内存错误及避免方法

```c
#include <stdio.h>
#include <stdlib.h>

void memoryLeakExample() {
    /* 
     * 内存泄漏示例
     * 分配内存后没有释放
     */
    int *leakPtr = (int *)malloc(10 * sizeof(int));
    // 使用内存...
    // 忘记free(leakPtr)
}

void doubleFreeExample() {
    /* 
     * 双重释放示例
     * 同一块内存被释放两次
     */
    int *doublePtr = (int *)malloc(sizeof(int));
    free(doublePtr);
    // free(doublePtr);  // 错误: 第二次释放
}

void useAfterFreeExample() {
    /* 
     * 释放后使用示例
     * 内存被释放后继续使用
     */
    int *afterPtr = (int *)malloc(sizeof(int));
    *afterPtr = 42;
    free(afterPtr);
    // printf("%d\n", *afterPtr);  // 错误: 释放后使用
}

void nullPointerDereference() {
    /* 
     * 空指针解引用示例
     * 对NULL指针解引用
     */
    int *nullPtr = NULL;
    // printf("%d\n", *nullPtr);  // 错误: 解引用空指针
}

void correctMemoryUsage() {
    /* 
     * 正确的内存使用方式
     */
    int *ptr = NULL;
    
    // 1. 分配内存后检查
    ptr = (int *)malloc(5 * sizeof(int));
    if (ptr == NULL) {
        printf("内存分配失败!\n");
        return;
    }
    
    // 2. 使用内存
    for (int i = 0; i < 5; i++) {
        ptr[i] = i * 10;
    }
    
    // 3. 释放内存前检查
    if (ptr != NULL) {
        free(ptr);
        ptr = NULL;  // 4. 释放后将指针置NULL
    }
    
    // 5. 避免使用已释放的指针
    // if (ptr != NULL) { ... }  // 安全检查
}

int main() {
    // 演示错误示例(实际运行时应注释掉)
    // memoryLeakExample();
    // doubleFreeExample();
    // useAfterFreeExample();
    // nullPointerDereference();
    
    correctMemoryUsage();
    return 0;
}
```

## 二十一、高级指针技术

### 1. 函数指针详解

```c
#include <stdio.h>

// 普通函数
int add(int a, int b) {
    return a + b;
}

int subtract(int a, int b) {
    return a - b;
}

int multiply(int a, int b) {
    return a * b;
}

int divide(int a, int b) {
    if (b != 0) return a / b;
    return 0;
}

// 回调函数示例
void calculate(int x, int y, int (*operation)(int, int)) {
    int result = operation(x, y);
    printf("结果: %d\n", result);
}

int main() {
    /* 
     * 函数指针声明
     * 语法: 返回类型 (*指针名)(参数类型列表)
     */
    int (*funcPtr)(int, int);
    
    // 指向add函数
    funcPtr = &add;  // 或 funcPtr = add;
    
    /* 
     * 通过函数指针调用函数
     * 语法1: (*指针名)(参数)
     * 语法2: 指针名(参数)
     */
    int sum = (*funcPtr)(10, 5);  // 传统方式
    printf("10 + 5 = %d\n", sum);
    
    int sum2 = funcPtr(20, 30);   // 简化方式
    printf("20 + 30 = %d\n", sum2);
    
    /* 
     * 函数指针数组
     */
    int (*operations[4])(int, int) = {add, subtract, multiply, divide};
    char *opNames[] = {"加法", "减法", "乘法", "除法"};
    
    int a = 15, b = 3;
    for (int i = 0; i < 4; i++) {
        printf("%s: ", opNames[i]);
        printf("%d %s %d = ", a, 
               (i == 0) ? "+" : (i == 1) ? "-" : (i == 2) ? "*" : "/", b);
        int result = operations[i](a, b);
        printf("%d\n", result);
    }
    
    /* 
     * 回调函数使用
     */
    printf("\n回调函数示例:\n");
    calculate(100, 20, add);
    calculate(100, 20, subtract);
    calculate(100, 20, multiply);
    calculate(100, 20, divide);
    
    return 0;
}
```

### 2. 复杂指针解析

```c
#include <stdio.h>

int main() {
    /* 
     * 复杂指针解析
     */
    int var = 42;
    
    // 1. 普通指针
    int *ptr1 = &var;
    
    // 2. 指向指针的指针
    int **ptr2 = &ptr1;
    
    // 3. 指针数组
    int *ptrArray[3];
    ptrArray[0] = &var;
    ptrArray[1] = ptr1;
    ptrArray[2] = *ptr2;
    
    // 4. 数组指针(指向数组的指针)
    int arr[5] = {1, 2, 3, 4, 5};
    int (*arrPtr)[5] = &arr;  // 指向整个数组的指针
    
    // 5. 函数指针数组
    void (*funcPtrArr[3])(void);  // 3个函数指针的数组
    
    printf("变量 var = %d\n", var);
    printf("指针 ptr1 指向的值 = %d\n", *ptr1);
    printf("指针的指针 ptr2 指向的值 = %d\n", **ptr2);
    
    printf("\n指针数组内容:\n");
    for (int i = 0; i < 3; i++) {
        printf("ptrArray[%d] = %d\n", i, *ptrArray[i]);
    }
    
    printf("\n数组指针访问:\n");
    printf("(*arrPtr)[2] = %d\n", (*arrPtr)[2]);  // 访问数组元素
    
    /* 
     * const与指针
     */
    const int constant = 100;
    // constant = 200;  // 错误: 不能修改const变量
    
    // 指向常量的指针
    const int *ptrToConst = &constant;
    // *ptrToConst = 200;  // 错误: 不能通过指针修改
    
    // 常量指针(指针本身不可变)
    int *const constPtr = &var;
    *constPtr = 200;  // 可以修改指向的值
    // constPtr = &constant;  // 错误: 不能修改指针
    
    // 指向常量的常量指针
    const int *const constPtrToConst = &constant;
    // *constPtrToConst = 300;  // 错误
    // constPtrToConst = &var;   // 错误
    
    return 0;
}
```

## 二十二、多文件编程与头文件

### 1. 多文件项目结构

**math_operations.h (头文件)**
```c
#ifndef MATH_OPERATIONS_H  // 防止头文件重复包含
#define MATH_OPERATIONS_H

/*
 * 函数声明
 * 头文件只包含声明，不包含实现
 */
int add(int a, int b);
int subtract(int a, int b);
int multiply(int a, int b);
float divide(int a, int b);

#endif
```

**math_operations.c (源文件)**
```c
#include "math_operations.h"  // 包含对应的头文件

/* 
 * 加法实现
 */
int add(int a, int b) {
    return a + b;
}

/* 
 * 减法实现
 */
int subtract(int a, int b) {
    return a - b;
}

/* 
 * 乘法实现
 */
int multiply(int a, int b) {
    return a * b;
}

/* 
 * 除法实现
 */
float divide(int a, int b) {
    if (b == 0) {
        return 0.0f;  // 简单处理除0错误
    }
    return (float)a / b;
}
```

**main.c (主程序)**
```c
#include <stdio.h>
#include "math_operations.h"  // 包含自定义头文件

int main() {
    int x = 10, y = 3;
    
    printf("%d + %d = %d\n", x, y, add(x, y));
    printf("%d - %d = %d\n", x, y, subtract(x, y));
    printf("%d * %d = %d\n", x, y, multiply(x, y));
    printf("%d / %d = %.2f\n", x, y, divide(x, y));
    
    return 0;
}
```

### 2. 编译多文件项目

```bash
# 编译所有源文件并链接
gcc main.c math_operations.c -o calculator

# 运行程序
./calculator
```

## 二十三、C语言最佳实践总结

1. **代码组织**
   - 合理使用头文件和源文件分离
   - 每个源文件应有对应的头文件
   - 头文件使用包含保护(#ifndef)

2. **命名规范**
   - 变量和函数使用小写加下划线：`calculate_sum`
   - 常量使用全大写：`MAX_SIZE`
   - 类型定义使用首字母大写：`typedef struct Node Node`

3. **错误处理**
   - 检查所有可能失败的系统调用
   - 检查内存分配是否成功
   - 使用返回值或errno报告错误

4. **内存管理**
   - 每个malloc对应一个free
   - 释放后将指针置NULL
   - 避免内存泄漏和悬空指针

5. **可移植性**
   - 避免使用平台特定的特性
   - 使用标准库函数
   - 注意数据类型大小差异

6. **性能考虑**
   - 减少不必要的内存分配
   - 使用局部变量而非全局变量
   - 优化循环和条件判断

7. **安全编程**
   - 检查数组边界
   - 验证用户输入
   - 使用安全的字符串函数

8. **文档和注释**
   - 为每个函数编写注释说明用途和参数
   - 解释复杂的算法和逻辑
   - 更新注释以保持与代码同步

通过以上全面而详细的学习，您应该已经掌握了C语言的核心概念和高级特性。C语言作为系统编程的基石，深入理解它将为您学习其他编程语言和系统开发打下坚实基础。
