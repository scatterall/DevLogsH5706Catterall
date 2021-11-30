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
