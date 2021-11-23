# DevLog 2
This week was about moving on from OCR and trialing and erroring TF_IDF. The overall feeling this week, for me, was that things are feeling smoother. I am making just as many mistakes, but I am learning how to identify more quickly and troubleshoot them on my own (aka I've been able to figure out certain error codes). I still rely HEAVILY on Dr. Graham and Chantal for help, but this week felt like more progreess was happening. So here are the main things that happened this week
1) So - after running through the OCR tutorial, Dr. Graham helped me by extracting the .txt files from the pngs, so I could move on to running the TF_IDF. OCR was a preparatroy step to get scanned documents readable by R Studio. 
2) I definitely hit some hiccups on the way. The first time I ran TFIDF on my scans (250 pages), it was successful, but R Studio crashed right at the end (suffering a "fatal error"). But I wasn't upset because the code ran really smoothly and it felt like a really solid practice round.
3) The next thing I realized was that my TFIDF was yielding over 24 000 results (aka unique words), and a LARGE portion of them were in French (since they are all government documents). So I actually spent sometime this week learning more Excel formulas. I downloaded .csv files of 500 most common French words (and, in hindsight, that wasn't nearly enough) and learned some Excel formulas on how to delete carriage returns, add punctuation etc - and then, irony of ironies, it ended up being better to run all the French words as single lines anyways -- oops!. After that, I had to edit the "stopwords" list in TFIDF - I ran the "vanilla words" version and then the French version, but it only eliminated about 2000 words, leaving me with around 22 000. So I would like to run this again and find a more comprehensive list.
4) The last thing I noticed was how the TFIDF yielded results PER PAGE. This will be helpful, because I would like to be able to see what was being talked about WHEN. But that does treat each page as a silo, whereas I would also like to see the results across the whole corpus. IN GENERAL - what was being said? ALL of these documents are DND. So what words/scripts do we see occuring most frequently across all of these documents?
Next steps: I would like to:
	a) Eliminate more French words from the search
	b) Run the search to collate words from pages as well as the whole corpus
	c) Run the plots/visuals.
	d) Try topic modelling
	e) I also have an 800+pages document of scans. I'm intimidated about doing the whole process again - cleaning up the pngs, extracting the text etc. After that, I feel confident in the TFIDF, but a bit nervous about doing the first part again.
	
	
