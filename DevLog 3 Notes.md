## Dev Log 3 Notes

### November 23

To remind myself - Dr. Graham helped me generate a metadata.csv. I'm a bit confused but it's helping us to organize the emails by DATE. So - that means we could do a plot by what was being said THAT DAY on a certain subject. I think?

Captain's Log: Today's objective is to try and scrub even more French words from the .csv file. I haven't tried starting a TF-IDF from the .csv file, but that's what I'm going to try. 
I had a list of 500 popular French words - I'm going to try scrubbing even more. After that, perhaps I'll have more luck generating the plots.

So RStudio would not open. I cleared up memory, restarted the computer, and eventually uninstalled and reinstalled it. After that, I could get it running. However, as I'm trying to run the TF-IDF tutorial, I'm now getting errors that there is no "Corpus" function, which is part of the "tm package", which I DID install (as part of the TFIDF code). So what did I screw up?

WHAT WOULD IT BE LIKE FOR THINGS TO JUST WORK??? 

Okay well I feel like it was two steps forward, ALL THE WAY BACK. I think I've completely eff'd up my RStudio. Can't get it running in either desktop or cloud version. Dr. Graham has been so helpful as well and I honestly feel like this whole project is just me going in circles.

## I blew up my RStudio; here is what I've done to try and troubleshoot so far.
### 1) Reviewed these sites/thread
      a) https://community.rstudio.com/t/cant-install-tm-help/47968 - re: why won't 'tm' install?
      b) https://datascience.stackexchange.com/questions/13759/getting-error-in-rstudio-while-loading-a-package-tm
      c) https://stackoverflow.com/questions/46056740/how-to-install-package-tm-in-r-3-3-0
### 2) I tried to install the packages on R, before installing them on R STudio. It looked they like installed fine, but I got the same error code when I tried it again in RSTudio. The code is below.
> install.packages('tm')
--- Please select a CRAN mirror for use in this session ---
trying URL 'https://mirror.csclub.uwaterloo.ca/CRAN/bin/macosx/contrib/4.1/tm_0.7-8.tgz'
Content type 'text/plain' length 1102134 bytes (1.1 MB)
==================================================
downloaded 1.1 MB


The downloaded binary packages are in
	/var/folders/42/sk4bz6wj0ggg9_xxbcw9wjg00000gn/T//RtmpbMkihF/downloaded_packages
> install.packages('tidyverse')
trying URL 'https://mirror.csclub.uwaterloo.ca/CRAN/bin/macosx/contrib/4.1/tidyverse_1.3.1.tgz'
Content type 'text/plain' length 421072 bytes (411 KB)
==================================================
downloaded 411 KB


The downloaded binary packages are in
	/var/folders/42/sk4bz6wj0ggg9_xxbcw9wjg00000gn/T//RtmpbMkihF/downloaded_packages
> install.packages('tidytext')
trying URL 'https://mirror.csclub.uwaterloo.ca/CRAN/bin/macosx/contrib/4.1/tidytext_0.3.2.tgz'
Content type 'text/plain' length 3046922 bytes (2.9 MB)
==================================================
downloaded 2.9 MB


The downloaded binary packages are in
	/var/folders/42/sk4bz6wj0ggg9_xxbcw9wjg00000gn/T//RtmpbMkihF/downloaded_packages
> install.packages('magrittr')
trying URL 'https://mirror.csclub.uwaterloo.ca/CRAN/bin/macosx/contrib/4.1/magrittr_2.0.1.tgz'
Content type 'text/plain' length 224637 bytes (219 KB)
==================================================
downloaded 219 KB


The downloaded binary packages are in
	/var/folders/42/sk4bz6wj0ggg9_xxbcw9wjg00000gn/T//RtmpbMkihF/downloaded_packages
> install.packages('ggplot2')
trying URL 'https://mirror.csclub.uwaterloo.ca/CRAN/bin/macosx/contrib/4.1/ggplot2_3.3.5.tgz'
Content type 'text/plain' length 4125542 bytes (3.9 MB)
==================================================
downloaded 3.9 MB


The downloaded binary packages are in
	/var/folders/42/sk4bz6wj0ggg9_xxbcw9wjg00000gn/T//RtmpbMkihF/downloaded_packages
> 
> library(tm)
Loading required package: NLP
> library(tidyverse)
── Attaching packages ────────────────────────────────────── tidyverse 1.3.1 ──
✔ ggplot2 3.3.5     ✔ purrr   0.3.4
✔ tibble  3.1.6     ✔ dplyr   1.0.7
✔ tidyr   1.1.4     ✔ stringr 1.4.0
✔ readr   2.0.2     ✔ forcats 0.5.1
── Conflicts ───────────────────────────────────────── tidyverse_conflicts() ──
✖ ggplot2::annotate() masks NLP::annotate()
✖ dplyr::filter()     masks stats::filter()
✖ dplyr::lag()        masks stats::lag()
> library(tidytext)
> library(magrittr)

Attaching package: ‘magrittr’

The following object is masked from ‘package:purrr’:

    set_names

The following object is masked from ‘package:tidyr’:

    extract

> library(ggplot2)

### 3) I tried to manually install, by navigating to "Packages" in R Studio, selecting the ones I want to install, but nothing.

I've been reading a bit about CRAN? I'm not sure I understand that - is it a repository of R Studio packages.

In preparation for a meeting with Dr. Graham on Tuesday, I have downloaded TeamViewer.

I'm wondering if the topic modelling code might work, even if the TF-IDF packages aren't downloading right now.
