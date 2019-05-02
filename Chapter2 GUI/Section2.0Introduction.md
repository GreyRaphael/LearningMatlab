# MATLAB GUI Introduction

GUI实现方式:
- 简单GUI用底层代码实现
- 复杂GUI用`guide`实现
- Matlab未来gui使用`appdesigner`

```bash
# in command window
guide

# working directory
untitled.m
untitled.fig
```

untitled.m分为4部分
- 主函数
- 打开函数(OpeningFcn)
- 输出函数(OutputFcn)
- 各种回掉函数(Callback)
> ![](res/gui01.png)

example: pushbutton1的text转移到pushbutton2

```matlab
% untitled.m只写了Callback部分
% --- Executes on button press in pushbutton1.
function pushbutton1_Callback(hObject, eventdata, handles)
set(handles.pushbutton2, 'string', get(handles.pushbutton1, 'string'));

% --- Executes on button press in pushbutton2.
function pushbutton2_Callback(hObject, eventdata, handles)
% hObject    handle to pushbutton2 (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)
```

example: 临时生成pushbutton
> openningFcn加入临时pushbutton，界面的创立发生在openningFcn之前(已经建立了handles)，所以要用guidata更新handles

```matlab
% untitled.m 只写了OpeningFcn和Callcak函数部分
function untitled_OpeningFcn(hObject, eventdata, handles, varargin)
handles.output = hObject;

h=uicontrol('tag', 'tempBtn', 'string', 'newBtn', 'callback', {@tempBtn_Callback, handles});
handles.tempBtn=h;

% Update handles structure
guidata(hObject, handles);

% --- Executes on button press in pushbutton1.
function pushbutton1_Callback(hObject, eventdata, handles)
set(handles.tempBtn, 'string', 'from btn1')

function tempBtn_Callback(hObject, eventdata, handles)
set(handles.pushbutton1, 'string', 'from temp btn');
```