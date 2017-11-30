# C++
[Tutorial](http://www.cplusplus.com/files/tutorial.pdf)

## Basic
| code | desc |
|:----:|:-----|
| // foo bar | コメント |
| #include <iostream> | `#`で始まる行はプロセッサへの`directive`  このケースでは`iostream`をファイルに含めるように命令している |
| using namespace std; | C++では標準ライブラリは`namespace`を利用して呼び出される |
| int main() | 関数定義の開始を意味する |
| cout << "Hello, world!" | C++ の`statement` |
| return 0; | リターン文 |

## Compile
+ `g++`を利用する.
+ [このサイト](http://kaworu.jpn.org/cpp/g++)でいろいろセッティング方法を調べた

### make binary file
```
$ g++ foo.cpp -o foo
$ g++ foo.cpp -g # show debug info
$ g++ -c foo.cpp # create object file
```

## Identifiers
識別子(変数名)は長さが1以上の文字, 数字, アンダースコアから構成される.
スペースや！は変数名として利用できない.
また、変数名は`_`や数字から始めることができない.
いや, 厳密には`_`からは始めることができるが, 処理系のキーワードとして予約されている可能性があるので
利用しない方が良い.

### Case sensitive
C++では文字の大小を区別する.
したがって`foo`と`Foo`は別物.

## Data types
| name | desc | size |
|:----:|:-----|:-----|
| char | 文字 | 1byte |
| short | 小さい整数 | 2bytes |
| int | 整数 | 4bytes |
| long | 大きい整数 | 4bytes |
| bool | 真理値 | 1byte |
| float | 小数 | 4byte |
| double | 長い小数 | 8byte |
| wchar_t | マルチバイト文字 | 2 or 4byte |

## Declare variables
```cpp
int a, b, c // こういう書き方もできる
unsigned short NumberOfSisters; // 必ず0以上 これは助かる
```

変数の宣言時には, 値を代入しておくことも可能.

```cpp
int a = 10;
```

## String class
`Data types`を見ればわかるように, C++にはString型がデフォルトで存在するわけではない.
文字列を利用したい場合は, `<string>`ライブラリを`include`すれば良い.

```cpp
#include <iostream> // iostreamライブラリをインクルード
#include <string>   // stringライブラリをインクルード
using namespace std;

int main() {
  string mystring = "This is a string";
  cout << mystring;
  return 0;
  }
```

## Escape code
| code | desc |
|:----:|:-----|
| \n | new line |
| \r |  carriage return |
| \t | tab |
| \v | vertical tab |
| \b | backspace |
| \a | aleat |

## Boolean
`bool`型のリテラルとしては`true`と`false`が存在する.

## Define constants
`#define`を利用することで定数を定義することができる.
定数は大抵大文字の`FOO`といった感じで定義されるらしい.

また, `const`修飾子を利用して特定の型の定数を定義することもできる.

```cpp
const int pathwidth = 100;
```

## Logical operators
| operator | deac |
|:---------|:-----|
| ! | NOT |
| && | AND |
|   | OR |

### Conditional operator
```cpp
7 == 2 + 5 ? 4 : 3; // returns 4
```

## I/O standard library
### Standard Output
C++では, 標準出力にアクセスするための変数は`cout`で与えられる.
`cout`は普通`<<`(挿入演算子)と一緒に利用される.

また, 1行に複数回`<<`を利用することもできる.

```cpp
cout << 3193 // prints number 120 on screen
cout << "moriaki" << 3193
```

`cout`は自動的に改行を挟んでくれない. 明示的に改行コード`\n`を末尾に付与するか, 
`endl`(manipulator)を挿入する必要がある.

### Standard Input
`cin` manipulatorを利用すれば良い.
`cout`とは対照的に, `>>`(抽出演算子)と一緒に利用される.

```cpp
int age;
cin >> age; // ←なんか変な書き方だ
```

### sstream header file
文字ではなく文字列を標準入力から受け取りたい場合に利用する.

### 行全体を入力として受け取りたい
`getline`関数を利用しよう. `cin`を通じて行を受け取ることができる.

`getline(cin, mystr) // mystrはstring型`というように利用することができる.

## memo
+ オブジェクトファイル
