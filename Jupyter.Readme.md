1. save a shell file in the serve: open_jupyter
```
#!/usr/bin/env bash

if [ "$#" -lt 1 ]; then
    PORT=8999 # default port
else
    PORT=$1
fi

echo After jupyter notebook is runing,
echo please run the following command in your local machine:
echo "open -a safari http://localhost:$PORT; ssh -NL localhost:$PORT:localhost:$PORT td"
jupyter notebook --no-browser --port=$PORT --ip=127.0.0.1
```
2. run this file in the serve: ./open_jupyter (this file is in /tigress/enhuil/)
3. input in local pc:
```
ssh -NL localhost:8999:localhost:8999 enhuil@tigressdata2.princeton.edu
```
4. copy and paste link provided from step 2 to the google chrome.

```
http://127.0.0.1:8999/?token=c2e4fa2a18e2b31f5344ee639549b643ab2cec4b1ce9e184
```
