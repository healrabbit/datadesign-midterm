# Data and Design Python Midterm

Digital sort tool for my rekordbox library 

rekordbox is a program that I use to DJ with, and as I am still learning, I often have difficulty sorting through my large collection to find acceptable songs to try and mix with the song I'm currently working with. There are two things that must match for a mix to be succesful: BPM(Beats Per Minute) and Key. rekordbox kind of has a "sort by" tool, but it only works for one category at a time, and just reorders the tracks in the collection instead of isolating ones that match the selected track. 

For my project I wanted to find a way to make the search tool that I needed to easily find songs to try out, and found out that you can export your entire rekordbox collection as a .xml file. I had no idea how to work with .xml files, but I found a program that can turn them into dictionaries: xmltodict. I used this to turn my xml file into a dictionary, which was more familiar had worked with these in class. It was a nested dictionary with a lot of unneccesary keys, so I searched through the layers of keys until I found the one I needed, 'Track'. 

I made a dataframe with everything within this key, but when I looked at the table, I found that the stock loops that appear in the collection by default were included, so I figured out which rows these were in, and indexed the data to get only the rows I needed. 

From there, I cleaned up the data to only include track name, bpm, and key. Since the songs in my collection were all files I got from youtube video to mp3 converters, some had extra information in the title (such as "Official Audio", or "Lyric Video", and I had never bothered to clean it up within the rekordbox program. Because the track name data was not easily cleanable, I decided the lookup paramaters for this tool would only be BPM and Key, and it would be used when I already had a first song, and just needed to find one that matched.

Upon my first try using comparisons on the bpm column, I got errors and realized that the bpm values were not in float format. I changed them and after that it went smooth! I used two input values for bpm, since many were analyzed to have decimal values, and may not match exactly but could be easily tweaked by slowing or speeding up a song. I just wanted songs that were in a similar range, so I wouldn't slow or speed up a song too much. I used one key value for key, as it was just an equal to text comparison. 

After testing it out, i set variables to each value and inputed that into my code, so values could be easily traded out. Once someone inputs the values into the variables, they just have to run that line, and then the line that indexes the dataframe, and they'd get a clean table with only the tracks that match! 

I added instructions so others could parse through my collection as well. If someone wanted to use their own collection, they can do so by exporting their rekordbox collection, making a copy of the notebook, importing their xml file to the notebook files, replacing the xml file path, and going through and running the lines of code from import down, double checking the line to remove stock loops if the index of the loops differs in their data, then running the top lines to use the tool. The ipynb file is in this repo, and the colab notebook link is here: https://colab.research.google.com/drive/1TTTZHlkCuE1dC3sY9hSfv5C9IDacXwER?usp=sharing. 

I tested this tool in a practice session and found it super helpful when I was stuck picking a file! I'm glad I could make something that was personal and useful to me. 


