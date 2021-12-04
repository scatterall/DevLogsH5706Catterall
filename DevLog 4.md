## DevLog 4
Okay - running through the code from Dr. Graham. 
I labelled my sc_data.csv file, text, date. So for the code:
sc_df <- tibble(id = data$X1, text = (str_remove_all(data$text, "[0-9]")), date = data$date) - I changed it to:
sc_df <- tibble(file = data$file, text = (str_remove_all(data$text, "[0-9]")), date = data$date). No error code so far. Just have to make sure that whatever is in the file matches what is in the code.

So the code up until this point (sc_df <- sc_df %>% replace_na(list(date = "Jan 01 1901"))) was just organizing the full text. But the tidy_step breaks it down by word (tidy_sc <- sc_df %>%
  unnest_tokens(word, text)) - ie, went from 202 obs to 5504 obs.
  
Ran this code to sort the word by frequency:
> sc_words <- tidy_sc %>%
  +     count(file, word, sort = TRUE)
head(sc_words)
And the most common word is "de" - French words. Can I run the French stopwords on this data? Okay, I'm going to try.
See script - it worked perfectly. I just had to make sure I edited the code to match the current dataset.

dtm <- sc_words %>%
  cast_dtm(id, word, n) - error code: Error in loadNamespace(x) : there is no package called ‘tm’
So, trying to fix. Ran install.packages('tm') and library. Fixed the error code.

> topic_proportion_per_day <- aggregate(theta, by = list(day = sc_df$day), mean)
Error in aggregate.data.frame(as.data.frame(x), ...) : 
  arguments must have same length
> 
> colnames(topic_proportion_per_day)[2:(K+1)] <- topicNames
Error in colnames(topic_proportion_per_day)[2:(K + 1)] <- topicNames : 
  object 'topic_proportion_per_day' not found
  
  I imagine that I am not inputting something I should be - there's probably a value missing?

## Dec 4
Okay - running the NEW topic modelling code from DrSG to remove French words.
Just ran: 
sc_df$text = removeWords(sc_df$text, stopwords("french"))

#turn sc_df into tidy format
# use `View(sc_df)` to see the difference
# from the previous table

But I don't see the difference. There were 202 entries before and after.

tidy_sc <- sc_df %>%
  unnest_tokens(word, text) - this resulted in 59000+ responses
  
tidy_sc <- tidy_sc %>%
  anti_join(stop_words) - this reduced it to 29000+ responses
  
sc_words <- tidy_sc %>%
  count(id, word, sort = TRUE) - this reduced it to 18000+
  
  # take a look at what you've just done
# by examining the first few lines of `cb_words` - when I run cb_words or View(cb_words), I get an error code (not found).

