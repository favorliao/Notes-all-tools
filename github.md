examples to use github to obtain MOM6

`
git clone -b $(MOM6_GIT_TAG) https://github.com/NOAA-GFDL/MOM6-examples.git mom6  

pushd mom6  

git checkout $(MOM6_GIT_TAG)  #needed for older git on zeus   

git submodule init src/MOM6 src/SIS2 src/icebergs tools/python/MIDAS   

git clone --recursive https://github.com/NOAA-GFDL/MOM6.git src/MOM6   

git clone             https://github.com/NOAA-GFDL/SIS2.git src/SIS2   

git clone             https://github.com/NOAA-GFDL/icebergs.git src/icebergs   

git submodule update #This gets the right version of submodules  

git diff lrgroup/default origin/lrgroup/dev

`
