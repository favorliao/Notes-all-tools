# Python
# plot figure
ds.fco2.sel(xh=slice(180,200)).sel(yh=slice(-5,5)).sel(time=slice("2000-1-1","2004-7-1")).mean("time").plot()
