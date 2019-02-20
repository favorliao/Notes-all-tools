# Ferret
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

## Fast plot figures using repeat: ferret -nodisplay
