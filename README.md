The Netstat Package
================
Steve Condylios
23/12/2019

`netstat` allows you to easily view which TCP ports are in use and which
are free to use.

Load library

``` r
# library(devtools)
# install_github("stevecondylios/netstat")
library(netstat)
```

### See which TCP ports are *in use*

``` r
ports_in_use()
```

    ##  [1] "40521" "57893" "24836" "57887" "1538"  "57726" "57628" "1025" 
    ##  [9] "1024"  "57473" "57460" "57342" "57341" "57291" "57340" "57292"
    ## [17] "27117" "52187" "52186" "50467" "9151"  "55630" "55628" "55626"
    ## [25] "9150"  "60380" "60379" "11170" "49154" "61086" "52156" "44617"
    ## [33] "29956" "29117" "29687" "45112" "30666" "5432"  "49157" "49156"
    ## [41] "49155" "49153" "53169" "63267" "51393" "58142" "5353"  "3722" 
    ## [49] "*"     "54261" "52802" "56947" "138"   "137"

### Find a free TCP port using `free_port()`.

``` r
# Display the TCP ports currently in use
free_port()
```

    ## [1] 14415

``` r
free_port(random=T)
```

    ## [1] 12654

  - `free_port()` returns a TCP port from Internet Assigned Numbers
    Authority (IANA) listed unassigned ports.

  - Any TCP port being used by the local machine will not be returned
    (so `free_port()` can be used for programatic port allocation in
    applications)
