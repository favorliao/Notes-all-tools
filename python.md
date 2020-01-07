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
close('all');figure(figsize=(8,3)); ds.temp.sel(time='2010-01').isel(zl=5).geo.cartoplot(cmap='jet')
```
This line close all the figures, set up figure size, plot the map with wenchang's geographic setup
```
fig, axes = plt.subplots(2, 2)
ds.temp.sel(time='2010-01', zl=5).plot(ax=axes[0,0])
ds.temp.sel(time='2010-01', zl=5).plot(ax=axes[0,1])
axes[0,0].set_title('')
axes[0,0].set_xlabe('')
```
These five lines plot the four maps in one figure

# plot figure
ds.fco2.sel(xh=slice(180,200)).sel(yh=slice(-5,5)).sel(time=slice("2000-1-1","2004-7-1")).mean("time").plot()

# find the location of installed python code
`python -c "import PyCNAL_regridding as pr; print(pr.__file__)"`
