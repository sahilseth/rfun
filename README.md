rfun
----------------------

> r-fun(ction): 
> attempt to make a **fun** cli for R



A small utility which wraps Rscript and provides access to **all** R functions from CLI.


## install:

Download and place in `~/bin`

```
chmod u+x ~/bin/rfun
export PATH=${PATH}:~/bin ## add to .bashrc
```


## Using a base package

```
## ------- load help for rnorm
rfun rnorm
## ------- sample from rnorm
rfun rnorm n=100
```



## Using a non-base package
### Loading a package automatically by `::`
```
## load help file for knitr
rfun knitr::knit
## OR use
rfun knitr::knit -h
```

### Lets process a Rmd file
```
## get path to an example Rmd file. Assuming we have knitr installed.
## ------- save the filename in a BASH variable rmd
rmd=$(rfun system.file package=knitr ...=examples/knitr-minimal.Rmd)
echo $rmd
## knit this awesome example !
rfun knitr::knit input=$rmd
```

#### Note:
This was originally build for `flowr` and is the derivative of this file:
[https://github.com/sahilseth/flowr/blob/master/inst/scripts/flowr](https://github.com/sahilseth/flowr/blob/master/inst/scripts/flowr)

I plan to keep these two in sync in case we find any bugs. In fact they are just alias on my systems.
