## My Notes
## concepts

## Docker Container
### Run
```
cd PythonImplementation
docker build --rm -t my_conda_proj .
docker run -p 8888:8888 -v `pwd`:/opt/notebooks my_conda_proj
```

### Run in docker shell
```
docker run -it -p 8888:8888 -v `pwd`:/opt/notebooks my_conda_proj /bin/bash

/opt/conda/bin/jupyter notebook --allow-root --notebook-dir=/opt/notebooks --ip=0.0.0.0 --port=8888 --no-browse
```

## Attach to existing docker session
```
docker ps
docker exec -it f9e212e83a22 /bin/bash
```

##### ref
https://github.com/JWarmenhoven/Coursera-Machine-Learning
