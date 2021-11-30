## DevLog 4
Okay - running through the code from Dr. Graham. 
I labelled my sc_data.csv file, text, date. So for the code:
sc_df <- tibble(id = data$X1, text = (str_remove_all(data$text, "[0-9]")), date = data$date) - I changed it to:
sc_df <- tibble(file = data$file, text = (str_remove_all(data$text, "[0-9]")), date = data$date). No error code so far. Just have to make sure that whatever is in the file matches what is in the code.

