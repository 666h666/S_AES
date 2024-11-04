# S_AES
3.1 第1关：基本测试
根据S-AES算法编写和调试程序，提供GUI解密支持用户交互。输入可以是16bit的数据和16bit的密钥，输出是16bit的密文。

![image](https://github.com/user-attachments/assets/323acfa7-3761-4dfe-968e-a3891e0e5fd4)


3.2 第2关：交叉测试
考虑到是"算法标准"，所有人在编写程序的时候需要使用相同算法流程和转换单元(替换盒、列混淆矩阵等)，以保证算法和程序在异构的系统或平台上都可以正常运行。
设有A和B两组位同学(选择相同的密钥K)；则A、B组同学编写的程序对明文P进行加密得到相同的密文C；或者B组同学接收到A组程序加密的密文C，使用B组程序进行解密可得到与A相同的P。

经过测试已实现


3.3 第3关：扩展功能
考虑到向实用性扩展，加密算法的数据输入可以是ASII编码字符串(分组为2 Bytes)，对应地输出也可以是ACII字符串(很可能是乱码)。

我们输入“Hello World”可以得到

![image](https://github.com/user-attachments/assets/3ab32d7e-a56d-4362-be1c-2f5c50ec9be5)

3.4 第4关：多重加密
3.4.1 双重加密
将S-AES算法通过双重加密进行扩展，分组长度仍然是16 bits，但密钥长度为32 bits。

将“Hello World”进行双重加密，得到
![image](https://github.com/user-attachments/assets/620f6d48-a791-491a-83b3-2ba3cff656c5)


3.4.2 中间相遇攻击
假设你找到了使用相同密钥的明、密文对(一个或多个)，请尝试使用中间相遇攻击的方法找到正确的密钥Key(K1+K2)。
现已知密码为
![image](https://github.com/user-attachments/assets/f5247e8a-6db4-4523-adfd-486edb2a0653)
我们将使用此密码得到的明密文对上传进行破解，得到
![image](https://github.com/user-attachments/assets/2e30f2ee-0566-4135-9f52-570c542c929e)
与设定一致

3.4.3 三重加密
将S-AES算法通过三重加密进行扩展，下面两种模式选择一种完成：
(1)按照32 bits密钥Key(K1+K2)的模式进行三重加密解密，
(2)使用48bits(K1+K2+K3)的模式进行三重加解密。

我们选择使用48bits进行三重加密，三个密码分别为
![image](https://github.com/user-attachments/assets/d0cda8bc-4e95-42ce-b267-6f8ccf55c574)
得到的结果为
![image](https://github.com/user-attachments/assets/74704014-6e18-4fa8-9f49-73821fd46c81)



