# MATLAB Environment

MATLAB Application:
- Numerical
- Symbol
- Plot
- Toolbox
- Programming
- Signal Analysis
- Simulink

MATLAB查找过程:
1. Variables
1. Functions
1. in Current Directory
1. in Search Directory

MATLAB path:
```matlab
% in command window
path
% C:\Users\Administrator\Documents\MATLAB
% C:\Users\Administrator\AppData\Local\Temp\Editor
% D:\MatlabR2018b\toolbox\...
% D:\MatlabR2018b\examples\...

cd 
% C:\Users\Administrator\Documents\MATLAB

userpath 
% ans = 'C:\Users\Administrator\Documents\MATLAB'

savepath % 通常配合userpath使用
pathtool
help path
```

where to run code:
- live editor(recommended):MATLAB live Editor非常强大，减少代码的结果窗口的来回切换
- command window
- M-file

New M-file:
- new a untitled m-file:
  `>>edit` or `Ctrl + N`
- new a named file in command window:
  `edit myTest`  
  在Editor中编辑myTest.m,然后在command window  
  `myTest`  
  就可以运行上面的myTest.m


MATLAB good examples:
- [find peaks](https://terpconnect.umd.edu/~toh/spectrum/SignalProcessingTools.html)

数据输出格式控制: format函数使用: `help format`

语法：`format +格式符`

只影响数据输出格式，不影响计算和存储

默认输出格式为`short`格式

```matlab
format short
a=0.5 % 0.500
format rat
a % 1/2
```