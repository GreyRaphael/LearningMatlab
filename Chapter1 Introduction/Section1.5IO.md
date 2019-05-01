# Matlab IO

- [Matlab IO](#matlab-io)
  - [read ascii](#read-ascii)

## read ascii

example: `load`

```bash
# data.txt
1 11
2 22
3 33
4 44
```

```matlab
data=load('data.txt')

% output
data = 4×2    
     1    11
     2    22
     3    33
     4    44
```

example: `fscanf`
> [io format Table](https://www.mathworks.com/help/matlab/ref/fscanf.html)

```bash
# data.txt load()无法读取，所以采用fscanf
1 11 111 1111
2 22
3 33
4 44
```

```matlab
clear;close all;

% open file
fid=fopen('data.txt','r');
% read
A=fscanf(fid, '%d')
% close file
fclose(fid);

% output
A = 10×1    
           1
          11
         111
        1111
           2
          22
           3
          33
           4
          44
```

example: `textscan`
> 读取多列

```bash
# data.txt
1 11 111 1111
2 22
3 33
4 44
```

```matlab
clear;close all;

% open file
fid=fopen('data.txt','r');
[A, pos1]=textscan(fid,'%d %d %d %d %d') % 故意设置5列
pos2=ftell(fid)
% close file
fclose(fid);

for i=1:5
    A{i}
end

% output
A = 
    {4×1 int32}    {4×1 int32}    {3×1 int32}    {3×1 int32}    {3×1 int32}

pos1 = 31
pos2 = 31
ans = 4×1 int32 column vector    
   1
   2
   3
   4

ans = 4×1 int32 column vector    
   11
   22
   33
   44

ans = 3×1 int32 column vector    
   111
     0
     0

ans = 3×1 int32 column vector    
   1111
      0
      0

ans = 3×1 int32 column vector    
   0
   0
   0
```

example: `textscan` remove headlines

```bash
# data.txt
This is headline1
This is headline2
1 11 111 1111
2 22
3 33
4 44
```

```matlab
clear;close all;

% open file
fid=fopen('data.txt','r');
A=textscan(fid,'%d %d %d %d %d', 'Headerlines', 2)
% close file
fclose(fid);
```

