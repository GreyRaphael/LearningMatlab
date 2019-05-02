# Matlab GUIDE

- [Matlab GUIDE](#matlab-guide)
  - [Introduction](#introduction)
  - [Data Transfer](#data-transfer)

## Introduction

example: 画三角函数
> properite inspector中设置axes的`nextplot`属性为`add`  
> ![](res/sincostan.png)

```matlab
% 忽略了其他函数， 之考虑OpeningFcn 和各种 Callback
function untitled1_OpeningFcn(hObject, eventdata, handles, varargin)
handles.output = hObject;

handles.x=-pi:0.01:pi;

% Update handles structure
guidata(hObject, handles);

function sin_Callback(hObject, eventdata, handles)
x=handles.x;
y=sin(x);
plot(handles.axes1,x,y,'b');

function cos_Callback(hObject, eventdata, handles)
x=handles.x;
y=cos(x);
plot(handles.axes1,x,y,'g');

function tan_Callback(hObject, eventdata, handles)
x=handles.x;
y=0.005*tan(x);
plot(handles.axes1,x,y,'r');

function clear_Callback(hObject, eventdata, handles)
delete(allchild(handles.axes1));
```

example: 菜单栏控制两种绘图模式
> ![](res/guiwithmenu.png)

```matlab
% --- Executes on button press in imageshow.
function imageshow_Callback(hObject, eventdata, handles)
axis(handles.axes2);
imshow('pout.tif');

% --- Executes on button press in clear.
function clear_Callback(hObject, eventdata, handles)
try
    delete(allchild(handles.axes1));
end

% --- Executes on button press in sin.
function sin_Callback(hObject, eventdata, handles)
ezplot(handles.axes1,'sin(x)');

% --------------------------------------------------------------------
function menu1_Callback(hObject, eventdata, handles)
h2=[handles.axes2 handles.imageshow];
set(h2,'visible','off');
h1=[handles.axes1 handles.sin handles.clear];
set(h1,'visible','on');
try
    delete(allchild(handles.axes2));
end

% --------------------------------------------------------------------
function menu2_Callback(hObject, eventdata, handles)
h2=[handles.axes2 handles.imageshow];
set(h2,'visible','on');
h1=[handles.axes1 handles.sin handles.clear];
set(h1,'visible','off');
try
    delete(allchild(handles.axes1));
end
```

example: gui with context menu
> step1: 设置menuEditor  
> step2: 设置properties inspector中的`UIContextMenu`为对应值

```matlab
figure('Menubar','none');
h=uicontextmenu;
uimenu(h,'label','context1');
uimenu(h,'label','context2');
set(gcf,'uicontextmenu',h);
```

Other gui related:
- gui with keyboard
- gui with mouse
- gui wth timer

## Data Transfer

