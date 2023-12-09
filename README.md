# 目录
  - [001 输出&计算]()
  - 



# 001 输出&计算
**1. 输出样例**
```C++
#include <iostream> // 输入输出
using namespace std;

int main(){
  // 输出字符串
  cout << "hello world" << endl;
  
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
#inlcude <cmath> // 数学计算

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

  cout << pow(2, 3) << endl; // 8 平方运算
  cout << sqrt(10000) << endl; // 100 开方运算
  cout << abs(-2) << endl; // 2 绝对值运算

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
# 数据类型
