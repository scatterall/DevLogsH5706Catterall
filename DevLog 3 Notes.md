## Dev Log 3 Notes

### November 23

To remind myself - Dr. Graham helped me generate a metadata.csv. I'm a bit confused but it's helping us to organize the emails by DATE. So - that means we could do a plot by what was being said THAT DAY on a certain subject. I think?

Captain's Log: Today's objective is to try and scrub even more French words from the .csv file. I haven't tried starting a TF-IDF from the .csv file, but that's what I'm going to try. 
I had a list of 500 popular French words - I'm going to try scrubbing even more. After that, perhaps I'll have more luck generating the plots.

So RStudio would not open. I cleared up memory, restarted the computer, and eventually uninstalled and reinstalled it. After that, I could get it running. However, as I'm trying to run the TF-IDF tutorial, I'm now getting errors that there is no "Corpus" function, which is part of the "tm package", which I DID install (as part of the TFIDF code). So what did I screw up?

### Code and Error message:
> a <- Corpus(DirSource("TFIDF/"),
+             readerControl=list(language="lat")) #lat = latin characters
Error in Corpus(DirSource("TFIDF/"), readerControl = list(language = "lat")) : 
  could not find function "Corpus"
> 

### WHAT WOULD IT BE LIKE FOR THINGS TO JUST WORK??? 

Okay well I feel like it was two steps forward, ALL THE WAY BACK. I think I've completely eff'd up my RStudio. Can't get it running in either desktop or cloud version. Dr. Graham has been so helpful as well and I honestly feel like this whole project is just me going in circles.

## November 24th: I blew up my RStudio; here is what I've done to try and troubleshoot so far.
### 1) Reviewed these sites/thread
      a) https://community.rstudio.com/t/cant-install-tm-help/47968 - re: why won't 'tm' install?
      b) https://datascience.stackexchange.com/questions/13759/getting-error-in-rstudio-while-loading-a-package-tm
      c) https://stackoverflow.com/questions/46056740/how-to-install-package-tm-in-r-3-3-0
      d) https://support.rstudio.com/hc/en-us/articles/200554786-Problem-Installing-Packages-in-the-RStudio-IDE
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

## November 25th
	1) Goals today: To a TF-IDF trial run using Rstudio.cloud
	2) If that is successful, try to run the TF-IDF again, using Dr. Graham's French stopwords recommendation.
	
### RSTUDIO.CLOUD
Okay - I've re-opened RStudio cloud and am realizing that the same issue exists there. Same error codes and everything.
I've uploaded a ZIP file with all the .txt scans. I ran the code to do the INSTALL. and LIBRARY. and got an error code --> "Error in library(ggplot2) : there is no package called ‘ggplot2’." I also tried the CORPUS code again - same error.
I'm throwing this one out to the Discord gang.

OKAY WE MADE A BREAKTHROUGH
scatterall — Today at 11:04 AM
Hi friends - just want to throw this one out to the R/RStudio/TF-IDF experts. My R Studio crashed a few days ago - I got an error message re: "incomplete/damaged" etc. Over a day and a bit, I tried rebooting, clearing up storage, and nothing. I eventually uninstalled and reinstalled R Studio (I didn't touch R, as far as I know). The software opened like a charm after, but I am now getting error codes as I try and move through the TF-IDF code. IE when I try and enter the following code:
a <- Corpus(DirSource("data/"),
            readerControl=list(language="lat")) #lat = latin characters
I get the following error message: Error in Corpus(DirSource("TFIDFzip/"), readerControl = list(language = "lat")) : 
  could not find function "Corpus"

This is an example of similar error codes, which I think have to do with problems downloading packages like tm, tidyverse, ggplot2 etc.
I'm trying it on Rstudio.cloud, and getting the same error code. Meeting Dr. Graham on Friday, but am wondering if anyone else has any thoughts? I'm assuming that, in my uninstallation, I uninstalled something I shouldn't have. Thanks all!
drgraham — Today at 11:08 AM
try install.packages(tm) wait, you say you get the same error in Rstudio.cloud? 
scatterall — Today at 11:12 AM
Yes
drgraham — Today at 11:46 AM
...off to investigate...
so, using Rstudio.cloud, i brought this zip file into the environment: https://graddh.netlify.app/data/data-for-tf-idf.zip by selecting the 'terminal' option....

and then used 'wget' and 'unzip' to get the materials...
scatterall — Today at 11:53 AM
aaaaah intresting, I uploaded a Zipfile using the Uploads under Files...
drgraham — Today at 11:53 AM

...which is one way; yes, you can use the uploads thing...
and then....
have to install the packages that I then call with the library() command....
including install.packages('topicmodels')
and then I run the code... and get the error you got, but then I fix that...

so library(tm) is the package that contains the Corpus function.
scatterall — Today at 11:57 AM
Okay so then are you installing/running library(tm) twice? It's included in that first piece of code for TF-IDF:
install.packages('tm')
install.packages('tidyverse')
install.packages('tidytext')
install.packages('magrittr')
install.packages('ggplot2')

library(tm)
library(tidyverse)
library(tidytext)
library(magrittr)
library(ggplot2)

So do you install it here, and then again?
drgraham — Today at 11:58 AM
when I started Rstudio.cloud there was a warning that they'd updated the base R, so I install everything I need, then with the library command I tell R Studio I'm going to use those packages.
scatterall — Today at 11:59 AM
Okay. I guess I'm wondering if I'm telling library twice - once for that initial install of everything I need, and then again after the corpus error code. I'll give it a run right now. I may have missed a step with the wget/unzip?
drgraham — Today at 12:00 PM
no you're not
I'm still not clear what you mean by 'telling library twice'
scatterall — Today at 12:02 PM
I might be getting confused. I'm going to try and run it as you suggested.
drgraham — Today at 12:04 PM
i restarted my project in R Studio, and instead of installing from the console or from a script, I'm using the 'install' button under 'packages' in the bottom right window. You might try that.
scatterall — Today at 12:05 PM
Okay, I'll try that after. I did try it yesterday, and didn't have luck. It was asking about CRAN? I was trying to do some reading on that.
drgraham — Today at 12:06 PM
CRAN is a repository for R packages; that's where the 'install.packages' command looks first. If you use the install button, it will ask you if you want to use CRAN or somewhere else. 9.9/10, CRAN's what you want.
scatterall — Today at 12:07 PM
Okay. So an improvement and a new error code. No longer says ERROR for Corpus, but that my directory is empty. I think I missed a step with the wget/unzip
drgraham — Today at 12:08 PM
interesting. I'm getting an error libicui18n.so.55: cannot open shared object file: No such file or directory which is related to the underlying operating system
drgraham — Today at 12:08 PM
what did you try to wget?
scatterall — Today at 12:09 PM
I didn't at all, I did a manual upload of the zip file
drgraham — Today at 12:09 PM
ok, so if you do that, then you have to make sure DirSource("path/to/folder/" is correct
you didn't wget/unzip at all! 😉
where's that damned file-upload thingy....
scatterall — Today at 12:11 PM
So I can wget files from my own device? Not only for web?
When I clik on the file (and it's set as my wd), I see all the .txt files there.
drgraham — Today at 12:12 PM
can you show me a screenshot of what you are clicking on to upload your files
ah shit, ok i see it
scatterall — Today at 12:13 PM
So I used the Upload tab you see here under Files, and you can see the TDIDFzip, and the beginning of the contents of the file. 

drgraham — Today at 12:13 PM
ok, and what does your Corpus command say
scatterall — Today at 12:14 PM
Error in DirSource("TFIDFzip/") : empty directory
drgraham — Today at 12:14 PM
no, what is the actual code you're running
scatterall — Today at 12:15 PM
a <- Corpus(DirSource("TFIDFzip/"),
            readerControl=list(language="lat")) #lat = latin characters
drgraham — Today at 12:15 PM
also, when you run getwd() what does it say
scatterall — Today at 12:15 PM
getwd()
[1] "/cloud/project/TFIDFzip"
drgraham — Today at 12:15 PM
that's why you're getting an error
you're already in TFIDFzip, but you're telling your machine that the data is in a subfolder of that folder.
change your wd to setwd("/cloud/project/")
scatterall — Today at 12:16 PM
Ah, I've made this mistake before
drgraham — Today at 12:17 PM
just did the upload button here, selecting a zip file; nice how it uploads and automatically unzips the folder.
scatterall — Today at 12:17 PM
BINGO
no more error code.

Okay, so I ran the whole TFIDF tutorial again and it all worked perfectly - except I got the same messed up plots, but that's not urgent.
SO plan is to eat lunch, and then try with the French stopwords from Dr. Graham.

## TODAY WAS A GOOD DAY!!
Got the error codes all fixed. Ran the tutorial all the way through again (I'm not really sure how I can jump in partway through (Dr. Graham is explaining it now). And then I ran the French stopwords code and it worked perfectly. Cut my results down to 18000+. 

So tomorrow - Topic modelling??

## Nov 27
First of all - helping Danielle troubleshoot some TFIDF issues she's having. When she runs the code data_words <- tidy_data %>%
  count(source, word, sort = TRUE), she gets the error Must group by variables found in .data.
* Column source is not found.
So she sent me her tidy_data file, and there is only one column - "word", but no "source". So trying to backtrack and see where it went missing.
Around df <- data.frame(text = get("content", a))
write.csv(df, "data.csv"), the sources disappear from her outputs (ie the .txt files).
Okay when she ran data <- read_csv("data.csv")
data <- tibble(source = data$X1, text = data$text), she didn't change "$X1" to the actual title of her column, which is "$...1". This has happened to me SOOO many times
The trick was to delete the old data.csv file and re-run the code, being sure to change the column title from the tutorial's code to the actual title of the column in her data.csv file.

It worked for her! EEEEEEP. I actually helped someone with CODE!!! WHAT THE EFF??

Next up - topic modelling, using Dr. Graham's adapted script.

## Nov 28
Okay - trying to do the topic modelling. I need to generate the sc_data.csv file that Dr. Graham created, which now organizes by DATE SENT. I've read through his instructions many times on how to do this. I have the TFIDF.csv file but I don't have the .csv of the day-sent.csv. And I can't really find the code that tells me how to generate this. I DO, however, have the DATES-IN-DOC.txt files, so I'm going to see if I can convert this into the .csv.
Except! I am noticing that my first_step_for_metadata.csv contains the same content as the day_sent.csv but without the duplicates. So what happens if I run THIS .csv file, instead of the DATES-IN-DOC.txt. - Okay no, I can't do that. The duplicate dates contain different content.

### Email I sent to Dr. Graham about the issue:
Hi Dr. Graham - I'm getting a bit stumped, and it has to do with the day-sent.csv file. To create the sc_data.csv, I have to merge the day-sent.csv with the TFIDF.csv. I have the latter file, but I'm a bit unsure as to how to create the day-sent.csv. I'm reading through the Discord chat, and you mentioned you created it using something called a regex? 

When I cross-reference the day-sent.csv with the first_step_for_metadata.csv you asked me to create, the document looks similar but the first_step_for_metadata does not include any repeating dates. When I cross-reference the day-sent.csv with the DATES-IN-DOC.txt file, I DO see the same structure (ie repeating dates, such as 
out_individual-pg-1.png-ocr.txt:Sent: May-22-19 2:00 PM
out_individual-pg-1.png-ocr.txt:Sent: May-22-19 1:43 PM.

So it seems as though I should be converting this .txt file to generate the day-sent.csv. I'm a bit thrown, however, because DATES-IN-DOC github contains TWO text files - one is more-dates.txt.

I think I can figure this out - I have such close variations of the data! I'm just a bit unsure about the regex process.
Best,
