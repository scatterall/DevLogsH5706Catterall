## DevLog 3

Overall, this week felt like a lot of steps backwards and sideways. Somehow, I broke my RStudio software on my computer and after 3-4 days, was finally able to get rstudio.cloud working, so I could move forward with everything!
BUT - I did have one really big personal win this week!

### What I Did
So the goals this week were to extract more French words and run topic modelling. At the beginning of the week, however, I kept getting error codes when I tried to open RStudio - "incomplete/damaged". 
After clearing up memory and restarting the computer, I eventually uninstalled and reinstalled it. After that, I could get it running. However, as I'm tried to re-run the TF-IDF tutorial, I kept getting errors that there is no "Corpus" function.
I wasn't able to fix it in RStudio, so I had to move over to rstudio.cloud, where I kept getting the same error. Dr. Graham walked me through it. I didn't realize I had to manually upload the file that would become my
working directory; once I did that, I had set my working directory incorrectly - one folder too far. After that, I was able to get rstudio.cloud running. For the full list of steps I took and error codes I had to navigate, 
you can read my Notes log at https://github.com/scatterall/DevLogsH5706Catterall/blob/main/DevLog%203%20Notes.md. Be warned, it is very rough!

Once I got that working, I ran the tutorial that Dr. Graham drafted on extracting even more French words. This cut my results down to 18 000 (which sounds like a lot, but is better than the 49 000 my TFIDF yields before I remove any stop words/clean up the data!

Moving on to topic modelling, I've hit some bumps. I KNOW that that I am so close to understanding it - I can feel it. Dr. Graham is helping me to understand the code/process behind creating a data sheet that yields results by DATE. He has
generated quite a few datasets and I can see how closely related they are - minor differences in between, but am just a bit lost in understanding some of the connecting code. 
So that is my goal this week - to successfully run topic modelling on the data.

### What I Learned
In some ways, it felt like a big step back, especially after last week where things felt like they were moving along a bit better. I had some medical issues pop up so that threw a wrench in my work plans as well.
But two WINS I want to note. Firstly, I really do feel like I'm in general starting to understand things better. My biggest barrier in this class has been learning the LANGUAGES of all these programs for the first time, and therefore struggling to understand clarifying instructions
or even how to ask a question. But Dr. Graham has sent me a few scripts and datasets and I am more able to understand what I am reading. I definitely still get confused/lost more often than not (that's why I don't always find message boards/reddit threads helpful - I can't understand 
the help they're offering!). BUT - I am noticing an improvement.

SECOND AND BIGGEST WIN (and evidence of the first win!). Another student in the class reached out to me for help with their TFIDF script/code. I was able to identify the issue and help them fix it! 
So that was probably my biggest win in the entire class so far!

### Next steps.
1) Successfully tackle running topic modelling on my datasets. I am also going back over all of my notes so far to start crafting my paradata.
