# Python

# load python in tigeressdata
```
source /scratch/gpfs2/GEOCLIM/wenchang/load_geoclim_python
ipython
```
# load data and plot figures
```
ds = xr.open_dataset('mom6_result_for_obc_new0-360.nc')
ds.temp.sel(time='2010-01').interp(zl=4).plot()
```
sel: actual value, such as time =year-month, depth=xx meter
isel: select i,j,k,l order number
interp: interpolate to a centain point
```
figure();ds.temp.sel(time='2010-01').isel(zl=5).plot(cmap='jet')
```
This line plot on a new figure; select time=2010-01 and sixth vertical layer, colormap=jet
```
clf();ds.temp.sel(time='2010-01',xh=200, method='nearest').sel(zl=slice(0,500)).plot(cmap='jet', yincrease=False)
```
This line plot a section along longitude(xh)=200E, depth from surface to 500 meters, reverse y coordinate
```
figure(figsize=(8,3)); ds.temp.sel(time='2010-01').isel(zl=5).geo.cartoplot(cmap='jet')
```
This 

# plot figure
ds.fco2.sel(xh=slice(180,200)).sel(yh=slice(-5,5)).sel(time=slice("2000-1-1","2004-7-1")).mean("time").plot()
