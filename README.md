# 目录
  - [001 输入输出与基本数学计算](https://github.com/SacredDreams/C-Notes/blob/main/README.md#001-输入输出与基本数学计算)
  - [002 数据类型](https://github.com/SacredDreams/C-Notes/blob/main/README.md#002-数据类型)
  - [003 if语句](https://github.com/SacredDreams/C-Notes/blob/main/README.md#002-003-if语句)
  - [004 循环](https://github.com/SacredDreams/C-Notes/blob/main/README.md#002-004-循环)


# 001 输入输出与基本数学计算
 [[返回目录]](https://github.com/SacredDreams/C-Notes/blob/main/README.md#目录)  

**1. 输出样例**
```C++
#include <iostream> // 输入输出

using namespace std;

int main(){
  // 输出字符串
  cout << "hello world" << endl; // 末尾endl用来换行，也可写作“cout << "hello world";”，即没有换行
  
  // 输入字符
  char ch;
  cin >> ch; // g 注意：若输入为数字，则输出为数字字符，而非数字
  cout << ch << endl; // g
  
  // 输出一个金字塔
  cout << "     *" << endl;
  cout << "    ***" << endl;
  cout << "   *****" << endl;
  cout << "  *******" << endl;
  cout << " *********" << endl;
  cout << "***********" << endl;

  return 0; // 程序结束
}
```

**2. 数学计算样例**
```c++
#include <iostream>
#include <cmath> // 数学计算
#include <iomanip> // 保留小数位数

using namespace std;

int main(){
  // 进行数学计算
  int a = 20, b = 10;
  double c = 5.22, d = 4.82;
  
  cout << a + b << endl; // 30
  cout << a - b << endl; // 10
  cout << a * b << endl; // 200
  cout << a / b << endl; // 2
  cout << 10 / 3 << endl; // 3 注意：计算结果舍弃小数点后所有数字，保留整数部分
  cout << a % b << endl; // 0
  cout << 10 % 3 << endl; // 1
  
  cout << c + d << endl; // 10.4
  cout << c * d << endl; // 25.1604 默认6位
  cout << c / d << endl; // 1.08299 默认6位

  cout << pow(2, 3) << endl; // 8 平方运算 注意：在接近临界值的时候，避免使用pow()函数
  cout << sqrt(10000) << endl; // 100 开方运算
  cout << abs(-2) << endl; // 2 绝对值运算
  
  cout << fixed << setprecision(5) << c << endl; // 5.22000 保留五位小数
  
  return 0;
}
```

**3. 拿取各个数位数字**
```c++
#include <iostream>

using namespace std;

int main(){
  int number = 123;

  cout << number / 100 << endl; // 拿取百位
  cout << number % 100 / 10 << endl; // 拿取十位
  cout << number / 10 % 10 << endl; // 拿取十位
  cout << number % 10 << endl; // 拿取个位
  return 0;
}
```

**4. 交换两变量数据**
```c++
#include <iostream>

using namespace std;

int main(){
  int a = 1, b = 2;
  int c = 3, d = 4;
  int e = 5, f = 6;
  int temp;
  
  // 方法一
  temp = a;
  a = b;
  b = temp;
  cout << a << ' ' << b << endl;

  // 方法二
  c += d; // c == 7
  d = c - d; // d == 3
  c -= d; // c == 4
  cout << c << ' ' << d << endl;

  // 方法三
  swap(e, f);
  cout << e << ' ' << f << endl;
  
  return 0;
}
```
# 002 数据类型
 [[返回目录]](https://github.com/SacredDreams/C-Notes/blob/main/README.md#目录)  

**1. 数据类型**
```c++
#include <iostream>

using namespace std;

int main(){
  /*
	  short 短整型          -32768 ~ 32767         有效位数：5     占用字节：2
	  int 基本整形          -2^31 ~ (2^31)-1       有效位数：10	  占用字节：4
	  long long 长整型      -2^63 ~ (2^63)-1       有效位数：19    占用字节：8
    flaat 单精度浮点型    -3.4e-38 ~ 3.4e+38     有效位数：7     占用字节：4
	  double 双精度浮点型   -1.7e-308 ~ 1.7e+308   有效位数：15    占用字节：8
	  long double 扩展双精度型
    char 字符型           256个不同字符                          占用字节：1
    bool 布尔型(True/False)
    const	常量
  */

  /*
  ASCII码表(举例)
	0	48
	1	49
	2	50
	......
	A	65
	B	66
	C	67
	......
	Z	90
	a	97
	b	98
	......
	*/
  
  // int 类型
	int max_i, min_i;
  
	max_i = 2147483647; // int最大值
	min_i = -2147483648; // int最小值
  max_i ++;
	min_i --;
	cout << max_i << endl << min_i << endl; // -2147483648 2147483647
  
  // long long 类型
  long long max_ll, min_ll;
	max_ll = 9223372036854775807;
	min_ll = -9223372036854775808;
	max_ll ++;
	min_ll --;
	cout << max_ll << endl << min_ll << endl; // -9223372036854775808 9223372036854775807
  
  // double 类型
  double d1 = 0.123456789, d2 = 123456789.123456789012345;
  cout << d1 << endl << d2 << endl; // 0.123457 1.23457e+008
  
  // float 类型
  float f = 3.14f;
  cout << f << endl; // 3.14
  
  // char 类型
  char c = 'c';
  cout << c << endl; // c
  
  // bool 布尔值
  bool b1 = 0, b2 = 1, b3 = 2;
  bool b4 = true, b5 = false;
  cout << b1 << endl << b2 << endl << b3 << endl << b4 << endl << b5 << endl; // 0 1 1 1 0 注意：转换时，true为1，False为0；0为false，其余数字均为true
  
  // const 常量
  const int value = 1; // 或者“int const value = 1;”，但切忌使用“value ++;”等操作改变其值
  cout << value << endl; // 1
  
  // 使用sizeof()函数计算占用字节
  short s = 12;
  int i = 12;
  cout << sizeof(s) << endl << sizeof(i) << endl; // 2 4
  
  return 0;
}
```
**2. 数据类型转换**
```c++
#include <iostream>

using namespace std;

int main(){
  // 数据类型隐式转换
  /*
	char + short = int → long long
	float + double = double
	*/
  char t_1 = 'a'; short t_2 = 100; int t_3 = 200; long long t_4 = 12345; double t_5 = 1.123456;
	cout << t_1 + t_2 << endl; // 197
  cout << t_2 + t_3 << endl; // 300
  cout << t_3 + t_4 << endl; // 12345
  cout << t_4 + t_5 << endl; // 12346.1
  cout << t_5 + t_1 << endl; // 98.1235
  
  // 数据类型强制转换
  double d1 = 3.1415926, d2 = 2.7182818;
  cout << (int)d1 << endl << int(d2) << endl; // 3 2
  
  return 0;
}
```
# 003 if语句
 [[返回目录]](https://github.com/SacredDreams/C-Notes/blob/main/README.md#目录)  

**1. 单层判断**
```c++
#include <iostream>

using namespace std;

int main(){
  // 简单的if判断
  /*
    当if中的内容成立，即为true时，执行内部代码，若不成立，即为false，则直接跳过
  */
  int num1;
  cin >> num1;
  
  if(num1 == 0){
    cout << "数字为0" << endl;
  }
  // 利用true或false判断，还可写为：
  if(!num1){ // 叹号“!”表示取反，num1本身为整形0，转换成bool后为false，为了使条件成立，需要进行取反操作，使其变为true
    cout << "数字为0" << endl;
  }
  if(num1 > 0){ // 取反“if(!(num1 > 0))”意思为“if(num1 <= 0)”
    cout << "数字大于0" << endl;
  }
  if(num1 < 0){ // 取反与上方同理
    cout << "数字小于0" << endl;
  }
  
  // 添加“否则”
  int num2;
  cin >> num2;
  
  if(!num2){
    cout << "数字为0" << endl;
  }else{
    cout << "数字不为0" << endl;
  }
  
  // 添加多条判断
  int num3;
  cin >> num3;
  
  if(!num3){
    cout << "数字为0" << endl;
  }else if(num3 == 1){
    cout << "数字为1" << endl;
  }else{
    cout << "数字既不是0，也不是1" << endl;
  }
  
  return 0;
}
```
**2. 嵌套判断**
```c++
#include <iostream>

using namespace std;

int main(){
  int num1;
  cin >> num1;
  
  if(num1 <= 10){ // 判断小于等于10的数字
    if(num1 % 2 == 0){
      cout << "偶数" << endl;
    }else{
      cout << "奇数" << endl;
    }
  }else if(num1 <= 20){ // 判断大于10小于等于20的数字
    if(num1 % 2){ // 如果取余2的结果为0（说明是偶数），那么是false，则不执行，如果取余2的结果不为0（说明是奇数），为true，则执行
      cout << "奇数" << endl;
    }else{
      cout << "偶数" << endl;
    }
  }
  
  return 0;
}
```
# 004 循环
 [[返回目录]](https://github.com/SacredDreams/C-Notes/blob/main/README.md#目录)  

**1. while循环**
