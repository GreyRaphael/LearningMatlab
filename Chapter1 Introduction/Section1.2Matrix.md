# Matrix

- [Matrix](#matrix)
  - [Generate Matrix](#generate-matrix)

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

