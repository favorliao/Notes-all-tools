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

## plot the box in the map
Usage : GO box xlo xhi ylo yhi [pen_number]
```
   yes? use coads_climatology
   yes? fill/x=100:300/y=-50:50/l=1 sst ! base plot
   yes? go box 180,220,-10,10,7         ! red thick rectangle
   yes? go box 170,230,-15,15,9         ! green thick rectangle
```
## If else then
```
LET runoff2 = IF runoff GT 0.4e-4 THEN 0.4e-4 else runoff
```
## Compute climatology and plot over
```
yes? LET uwnd_climatology = uwnd_of_interest[GT=month_reg@MOD]
yes? PLOT/X=180/Y=40/OVERLAY uwnd_climatology[T=15-jan-1983:15-jan-1991]
! Subtract to get the anomaly
! Regrid the anomaly back to the original time axis using @asn to guarantee
! success (Subtle interpolation errors may occur on irregular time axes 
! if the @asn regridding isn't done.)

yes? LET uwnd_anomaly = uwnd - uwnd_climatology[gt=uwnd@asn]
yes? PLOT/X=180/Y=40/T=15-jan-1983:15-jan-1991 uwnd_anomaly
yes? use my_current_data
yes? plot/X=180/Y=40 U

yes? LET U_climatology = U[GT=month_reg@MOD]
yes? PLOT/X=180/Y=40/OVERLAY U_climatology
 **ERROR: regridding: only @ASN, @LIN, or @NRST regridding between calendar types: NOLEAP, GREGORIAN
 yes? say `U,return=calendar` 
!-> MESSAGE/CONTINUE NOLEAP
NOLEAP

! Define the climatology accordingly,
yes? LET U_climatology = U[GT=month_noleap@MOD]
yes? PLOT/X=180/Y=40/OVERLAY U_climatology
```
[reference](https://ferret.pmel.noaa.gov/Ferret/faq/how-do-i-calculate-climatologies-and-climatological-anomalies)
