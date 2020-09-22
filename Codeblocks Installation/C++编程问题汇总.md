### Q & A

**1.int 和 short 都是4字节, 面对一个4字节是否有一个机制能区分它是什么类型（比如存在不同的地方）**

&emsp; 事实是，类型系统其实是为编译器服务的，用于类型推导、类型检查、组合类型、继承、派生等等，用于检查代码正确性、简化代码。而编译器做好这些类型检查的工作后，转到机器语言时，它们都脱掉了类型这个帽子，而只是单纯的寄存器变量罢了。因此程序在 运行 期间 ，没有 类型 这个约束。在 CPU 看来，int 变量只是存储在寄存器上的4字节的值。

&emsp; 对于机器来说，它只知道命令和对象，并不知道4字节对象是float还是int。但是指令是有针对性的。譬如整型加法是ADD，浮点加法是ADDSD之类的。因此，编译器只需要将变量要执行的运算翻译成对应于其类型的机器指令，而对于机器而言，无需再为“类型”去额外存储信息了。

**2.为什么不同计算机能运行同一个C++程序，而不能运行同一个汇编程序?**

&emsp; 汇编语言使用的指令往往是和机器的硬件的体系结构有关，譬如x64和arm平台的机器指令都是不同的。具体细节可以等学了嵌入式这门课就知道了。

**3.main 函数是啥？其参数是干啥的？**

&emsp; 程序应当含有一个名为 main 的全局函数，它被指定为程序的启动点。它应当有下列形式之一：

    int main () {body}
    int main (int argc, char *argv[]) { body }	(2)	

    argc	-	非负数，表示从程序运行的环境传递给程序的实参个数。
    argv	-	指针，指向包含 argc + 1 个指针的数组的首元素。数组末元素为空指针，若其前面有任何元素，则它们指向空终止多字节字符串，表示从执行环境传递给程序的若干参数。若 argv[0] 不是空指针，或等价地 argc > 0 ，则它指向表示用于调用程序的名称的字符串，或空字符串。
    body	-	main 函数的函数体

**4.如何计算立方根？**
&emsp; 编译开启 -std=c++11 或者更新的标准之后，可以使用 cbrt 函数

&emsp; 否则，使用传统的 pow 函数，但要注意符号问题。

&emsp; 其签名分别为

    float cbrt(float arg); // cbrt(x)  x 可以为任意实数
    float pow ( float base, float exp ); // pow(x, 1.0/3) 注意 x 需非负
    
    
### C++语法问题
**引用自己实现的头文件应使用双引号而非尖括号**

    #include "my_headers.h" // OK

**指针的声明问题。**

    Node* p1, p2, p3; // 注意p2, p3类型不是 Node*

**cin.get(), cin.getline() , cin >> 问题。**

&emsp; OJ上一般不推荐使用 cin.get() ，理由是get遇到界定符时,停止执行,但并不从流中提取界定符（如换行符）,再次调用会遇到同一个界定符,函数将立即返回,不会提取输入，导致程序运行异常。

**数组如何作为函数参数。**

&emsp; 数组做参数时会直接被隐式转化为指针。如下声明是等价的

    void f(int []);
    void f(int *);

&emsp; 虽然也可以写出数组大小 void f(int [10]);，但是不推荐。二维数组有void f(int [][10])的写法，亦不推荐。

**函数默认参数问题。**

&emsp; C++规定默认参数只能在声明或者定义中出现一次。一般建议将默认参数写在声明中。

    struct Array {
	    Array(int capacity=10);
    };

    Array::Array(int capacity=10) {} // 错误
    Array::Array(int capacity) {} // OK

**函数存在无返回值的可能性。**

&emsp; 忘记写返回，如赋值运算符重载忘记返回*this。或者没有管辖到条件分支的所有情况。

    int f(int x) {
	    if (x == 0) return 0;
        // warning: control reaches end of non-void function [-Wreturn-type]
    }

**前置函数声明，在后面实现函数时，函数签名不匹配。(const，&修饰符)**

&emsp; 例如

// 前置的函数声明
bool search(const int&) const;

// 后置函数实现
// void search(const int&) const {...}; 错误，函数签名不匹配
// bool search(int&) const {...}; 错误，函数签名不匹配
// bool search(const int) const {...}; 错误，函数签名不匹配
// bool search(const int&) {...}; 错误，函数签名不匹配
bool search(const int&) const {...}; // OK
C++的赋值都是值传递。体会差别：

struct Node { 
    int data;
	Node* next;
    Node(int d=0): data(d) {}
};

Node* head = new Node();

// method 1
Node* next = head->next; next = new Node(); 
与

// method 2
head->next = new Node();
只有方法2可以正确的构造新节点。









