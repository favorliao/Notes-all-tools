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
ssh -NL localhost:8999:localhost:8999 enhuil@tigressdataprinceton.edu
```
