# rfun
Simple Utility providing CLI access to all R functions


`rfun` is a small utility which wraps Rscript and provides access to **all** R functions from CLI.


## install:

Download and place in `~/bin`

```
chmod u+x ~/bin/rfun
export PATH=${PATH}:~/bin ## add to .bashrc
```


## Using with a base package
### get help on rnorm

```
rfun rnorm
```

```
rfun rnorm n=100 x=2
```



## Using a non-base package
### Let us get a example Rmd file
```
rfun system.file package=knitr ...=examples/knitr-minimal.Rmd
## ------- save the filename in a BASH variable rmd
rmd=$(rfun system.file package=knitr ...=examples/knitr-minimal.Rmd)
echo $rmd
```

### Loading a package automatically by `::`
```
## load help file for knitr
rfun knitr::knit
## knit this awesome example !
rfun knitr::knit input=$rmd
```

## Note:
This was originally build for `flowr` and is the derivativeitive of this file:
[https://github.com/sahilseth/flowr/blob/master/inst/scripts/flowr](https://github.com/sahilseth/flowr/blob/master/inst/scripts/flowr)

I plan to keep these two in sync in case we find any bugs. In fact they are just alias on my systems.
