# Ferret
## Fast plot figures using repeat: 
```
ferret -nodisplay
```

## compute climatological value (monthly or daily mean)
```
yes? show axis/all
yes? LET uwnd_of_interest = uwnd[T=15-jan-1983:15-jan-1991]
yes? PLOT/X=180/Y=40 uwnd_of_interest
yes? LET uwnd_climatology = uwnd_of_interest[GT=month_reg@MOD]
yes? PLOT/X=180/Y=40/OVERLAY uwnd_climatology[T=15-jan-1983:15-jan-1991]
```
[reference](https://ferret.pmel.noaa.gov/Ferret/faq/how-do-i-calculate-climatologies-and-climatological-anomalies)

## set up the ratio of figure and quality
```
yes? set window /quality=high /aspect=0.5:axis 1 !0.5 is the y length
```

## Add extra search directory, take map nc as an example
```
1. vi .bashrc
2. add this line: export FER_DATA="/home/enhuil/ferret ./"
3. Download mapnc file and put it in /home/enhuil/ferret. 
```
map nc canbe download [here](http://ferret.pmel.noaa.gov/static/Demos/land_detail/geo_borders_intermed.nc)


