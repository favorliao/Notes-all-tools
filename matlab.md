# Notes-all-tools
## speed up loop
Do not use clear during the loop when you only want to clear very little variable.   




## figure with worldmap 


### 4x2 (colxrow)
```
set(gcf,'paperOrientation','portrait');
set_figure_size(gcf, '', [0.1 0.1 0.1 0.1],1.2,0.7);
xax=[0.08 0.51]; yax=[0.64 0.41 0.18 -0.05]; wax=[0.42]; hax=[0.45];
cpos=[0.06 0 0.5 1];
or
set(gcf,'paperOrientation','portrait');
set_figure_size(gcf, '', [0.1 0.1 0.1 0.1],1.2,0.7);
xax=[0.08 0.50]; yax=[0.61 0.39 0.17 -0.05]; wax=[0.4]; hax=[0.5];
cpos=[0.06 0 0.5 1];
```

### 3x3
```
set_figure_size(gcf, '', [0.1 0.1 0.1 0.1],1.2,0.7);
xax=[0.06 0.36 0.66]; yax=[0.58 0.31 0.04]; wax=[0.29]; hax=[0.38];
cpos=[0.05 0 0.5 1];
```

### 3x2
```
set(gcf,'paperOrientation','landscape');
set_figure_size(gcf, '', [0.1 0.1 0.1 0.1],1.0,0.8);
xax=[0.07 0.50]; yax=[0.68 0.40 0.12]; wax=[0.41]; hax=[0.27];
cpos=[0.06 0 0.5 1];
```

### 3x1
```
set(gcf,'paperOrientation','portrait');
set_figure_size(gcf, '', [0.1 0.1 0.1 0.1],1.0,0.8);
xax=[0.1]; yax=[0.66 0.36 0.06]; wax=[0.8]; hax=[0.325];
cpos=[0.08 0 0.5 1];
```

### 2x3
```
set(gcf,'paperOrientation','landscape');
set_figure_size(gcf, '', [0.1 0.1 0.1 0.1],1.2,0.52);
xax=[0.06 0.36 0.66]; yax=[0.5 0.12]; wax=[0.29]; hax=[0.38];
cpos=[0.05 0 0.5 1];
```

### 2x2
```
set(gcf,'paperOrientation','landscape');
set_figure_size(gcf, '', [0.1 0.1 0.1 0.1],1,0.53);
xax=[0.07 0.505]; yax=[0.49 0.05]; wax=[0.42]; hax=[0.5];
cpos=[0.06 0 0.5 1];
```

### 1x2
```
set(gcf,'paperOrientation','landscape');
set_figure_size(gcf, '', [0.1 0.1 0.1 0.1],1,0.335);
xax=[0.07 0.505]; yax=[0.1]; wax=[0.42]; hax=[0.9];
cpos=[0.06 0 0.5 1];
```

### 2x1
```
set(gcf,'paperOrientation','portrait');
set_figure_size(gcf, '', [0.1 0.1 0.1 0.1],1,0.56);
xax=[0.1]; yax=[0.09 0.53]; wax=[0.8]; hax=[0.4];
cpos=[0.08 -0.03 0.7 1.2];
```

### 1x1
```
set_figure_size(gcf, '', [0.1 0.1 0.1 0.1],1,0.325);
Xax=[0.1]; Yax=[0.1]; Wax=0.88; Hax=0.88;
cpos=[-0.03 0.13 0.5 1/1.43];
```
