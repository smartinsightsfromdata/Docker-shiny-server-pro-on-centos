#Docker for Shiny Server Pro configuration on Centos

Many organisations that are interested in shiny server pro may care for installing it on a supported version of linux like `RHEL`. 

This is a typical dev configuration as it includes in one docker configuration:

* R
* RStudio
* Shiny Server Pro

## Please note this is a prototype - currently not working


Build with (from the folder containing the Dockerfile):
```
docker build --force-rm=false --no-cache=true --tag="smartinsightsfromdata/shinypro" .
```

Test with (this will show the supervisor interactions to the console):
```
docker run -p 3838:3838 -p 8787:8787 -t -i smartinsightsfromdata/shinysrv
```

If you don't want to save the container, run with (you could also use -v to store on your host the shiny folder to use on the server):
```
docker run --rm  -p 3838:3838 -p 8787:8787  smartinsightsfromdata/shinysrv
```

###Acknoledgements: 
This work is based on the excellent work done by the people at rocker.org and Winston Chang at RStudio.