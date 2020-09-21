## 下载 codeblocks-20.03mingw-setup.exe
[交大云盘下载链接](https://jbox.sjtu.edu.cn/link/view/9f753b5137eb496388b32760df8ee67d)
## 安装
    1. 双击安装包：codeblocks-20.03mingw-setup.exe
    2. 点击：Next, I agree, Next, Install.

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/1.png)
![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/2.png)
![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/3.png)
![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/4.png)

    之后等待安装即可。

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/5.png)

    安装完成后提示是否马上运行，这里可以直接运行，也可以不马上运行。

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/6.png)

    点击Next，Finish安装就结束啦。

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/7.png)
![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/8.png)

## 第一次使用
### 文件关联Codeblocks的提示
    第一次使用可能会出现是否要进行C++/C源文件关联Codeblocks的提示。

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/9.png)

    建议初学者选择最后一项，全部关联。对其他IDE更熟悉的同学则可以根据自己的需求进行选择。

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/10.png)

### 新建一个C++项目

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/2-1.png)
![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/2-2.png)
![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/2-3.png)
![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/2-4.png)
![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/2-5.png)
![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/2-6.png)
![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/2-7.png)
![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/2-8.png)
![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/2-9.png)

### CodeBlocks如何进行简单的代码调试/Debug?
    Debug的功能：
    1. 提供运行时的中断处的局部变量和全局变量值
    2. 在运行时，观察中断处指定表达式的值
    这一节适合同学们在对编写C++代码较为熟悉之后的学习
    对于如下一段简单的代码，我们提供一份简单的代码调试指导
    
    #include <iostream>
    using namespace std;
    int sumCubic(int n) {
    // 计算 1^3 + 2^3 + ... + n^3
    int sum = 0;
    while (n) {
        sum += n * n * n;
        n--;
    }
    return sum;
    }
    int main()
    {
    for (int n = 0; n <= 10; ++n) {
        cout << "sumSquare(" << n << ") = " << sumCubic(n) << endl;
    }
    return 0;
    }

    将代码拷贝到你的项目里面（你可以新建一个项目，然后替换掉 main.cpp 里面的内容）
然后如图，鼠标单击行号即可设置中断点，打开**红色小三角形**开启调试。

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/3-1.png)

    如图，你会看到一个黄标运行到断点处。如图找到 蜘蛛形状的 Debugging Windows 选项，开启 Watches，然后便可以看到函数的局部变量的值了。

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/3-2.png)
![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/3-3.png)

    你也可以输入表达式，观察断点处表达式的值。

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/3-4.png)
    
    最后，可以点击红色的 X 退出 Debug。

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/3-5.png)

### 汉化

**汉化包链接**

[交大云盘下载链接](https://jbox.sjtu.edu.cn/link/view/add5e7c40dbb4f668af0f0f3fa48b85d)

汉化包是一个名为locale.zip的压缩包。

**解压汉化包**

    首先找到codeblocks的安装位置，点进share文件夹。
    
![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/4-1.png)

    然后点进codeblocks文件夹

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/4-2.png)

    在当前这个文件夹下解压汉化包

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/4-3.png)

    最终的汉化文件的位置应该如图所示，即locale\zh_CN\zh_CN.mo

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/4-4.png)

**配置Codeblocks**

- 打开Codeblocks，点击Setting->Environment

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/4-5.png)

- 点击View
- 勾选Internationalization
- 右侧下拉选择Chinese(Simplified)
- 点击OK即可

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/4-6.png)

- 重启Codeblocks即可看到汉化效果

![image](https://github.com/longsjtu/FAQ/blob/Programming---ideas-and-methods/Codeblocks%20Installation/images/4-7.png)



来源：https://github.com/OneForward/TACpp/blob/master/tutorials/CodeBlocks.md
