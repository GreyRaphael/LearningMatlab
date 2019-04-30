# Matrix

- [Matrix](#matrix)
  - [Generate Matrix](#generate-matrix)
  - [Matrix Reference](#matrix-reference)

## Generate Matrix

```matlab
% method1:by typing
A0=[1, 3, 5, 7]
% method2: init:step:end, [init, ..., end]
A1=1:2:7
A2=1:7
% method3: linspace, logspace
x1=linspace(1, 7, 4)
x2=logspace(2, 4, 3)
x3=logspace(1,pi,4) % very special

% output
A0 = 1×4    
     1     3     5     7

A1 = 1×4    
     1     3     5     7

A2 = 1×7    
     1     2     3     4     5     6     7

x1 = 1×4    
     1     3     5     7

x2 = 1×3    
         100        1000       10000

x3 = 1×4    
   10.0000    6.7980    4.6213    3.1416
```

## Matrix Reference

```matlab
% 1d
x=1:5
x(2)
x(2:4)
% 2d
A=reshape(1:20, 4, 5)
A(2:3,3:4)
A(2:3,:)
A(2,:)
A(2,3)
% 引用n维矩阵中的一个元素，需要n个角标

% output
x = 1×5    
     1     2     3     4     5

ans = 2
ans = 1×3    
     2     3     4

A = 4×5    
     1     5     9    13    17
     2     6    10    14    18
     3     7    11    15    19
     4     8    12    16    20

ans = 2×2    
    10    14
    11    15

ans = 2×5    
     2     6    10    14    18
     3     7    11    15    19

ans = 1×5    
     2     6    10    14    18

ans = 4×1    
     9
    10
    11
    12

ans = 10
```

```matlab
% generate 3d matrix
for i=1:2
    for j=1:3
        for k=1:4
            c(i, j, k)=i*j*k
        end
    end
end
```
