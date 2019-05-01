# Matlab Language

- [Matlab Language](#matlab-language)
  - [Grammar Introduction](#grammar-introduction)
    - [Data Type](#data-type)

## Grammar Introduction

> 各种计算机语言，基本语法的框架都比较一致，都包括数据类型、常变量定义、运算符种类、表达式定义、程序流程控制、函数定义、程序文件编写等几个方面。不同的语言，语法具体细节在规定上有所不同。

基本语法:
- 数据类型
- 常量与变量
- 运算符
- 表达式
- 语句
- 流程控制
- script file & function file

### Data Type

[MATLAB DataType](https://www.mathworks.com/help/matlab/data-types.html):
- Numeric: integer; single, double; 
- Logical
- character & string
- array & matrix
- date & time
- structures
- cell
- function handles
- java type

```matlab
% numeric type
a0=int8(123) % 123
a1=int16(123) % 123
a2=int32(123) % 123
a3=int64(123) % 123

b0=int8(256) % 127
b1=int8(-256) % -128
b2=int16(256) % 256
b3=int16(-256) % -256
```

```matlab
% logical type
a=logical(0) % false
b=logical(1) % true

a&b % false
a|b % true
~a % true
a>b % false
a<b % true
```

```matlab
% character & string type
a0='hello'
a1='1'
a2='1.23'
a3=a1+a2 % [98 95 99 100]
a4=[a1, a2] % '11.23'
a5=char(65) % 'A'
a6=char([97, 98]) % 'ab'
```

```matlab
% array & matrix type
a0=[1, 2, 3] % 结果出现在command window
a1=[4, 5, 6]; % 不会出现在command window
a2=[1, 2, 3; 4, 5, 6]
```

```matlab
% date & time
clock

% output
ans = 1×6
    2019	5	1	11	56	45.8180000000000
```

```matlab
% struct: 结构体myStruct.memberName=expression
a.x1=pi;
a.x2='string';
a.x3=1:10

%结构体操作
isstruct(a)
fieldnames(a)
isfield(a,'x2')
b=getfield(a,'x3')
c=rmfield(a,'x1')

% output
a = 
    x1: 3.1416
    x2: 'string'
    x3: [1 2 3 4 5 6 7 8 9 10]

ans = 
   1

ans = 
    {'x1'}
    {'x2'}
    {'x3'}

ans = 
   1

b = 1×10    
     1     2     3     4     5     6     7     8     9    10

c = 
    x2: 'string'
    x3: [1 2 3 4 5 6 7 8 9 10]
```

```matlab
% cell
a={12,pi,'string',1:4}

% output
a = 
    {[12]}    {[3.1416]}    {'string'}    {1×4 double}
```

```matlab
% function handles
c1='cos'
fh1=str2func(c1)

fh2=@sin
c2=func2str(fh2)

feval(fh1, pi)

functions(fh1)

% output
c1 = 'cos'
fh1 = 
    @cos

fh2 = 
    @sin

c2 = 'sin'
ans = -1
ans = 
    function: 'cos'
        type: 'simple'
        file: ''
```

```matlab
% datatype convert
db=pi;
class(db)
class(ans)
num=int32(db)
str='I am genius'
ch='a'
d=double(ch)
e=char(100)
eval('t=333')
f=str2num('365')
g=num2str(123456789)
whos

%output
ans = 'double'
ans = 'char'
num = 3
str = 'I am genius'
ch = 'a'
d = 97
e = 'd'
t = 333
f = 365
g = '123456789'
  Name      Size            Bytes  Class     Attributes

  ans       1x4                 8  char
  ch        1x1                 2  char
  d         1x1                 8  double
  db        1x1                 8  double
  e         1x1                 2  char
  f         1x1                 8  double
  g         1x9                18  char
  num       1x1                 4  int32
  str       1x11               22  char
  t         1x1                 8  double
```