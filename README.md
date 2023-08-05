A movie recommendation system is a fancy way to describe a process that tries to predict your preferred items based on your or people similar to you. It is a tool designed to predict/filter the items as per the user’s behavior.
Movie recommendation system can be of three types- Content-Based Filtering, Collaborative Filtering and Hybrid Recommendations.

The datasets contains two CSV files, credits, and movies. The credits file contains all the metadata information about the movie and the movie file contains the information like name and id of the movie, budget, languages in the movie that has been released, etc.

Start by importing the neccesary libraries such as numpy, pandas, sklearn, nltk, pickle etc. The next step is to merge the 'Movies' and 'Credits' Datasets on the basis of either 'movie_id' or 'movie_title'.

After merging, keep only those columns that are neccesary for the recommendation system such as Genre, Movie ID, keywords, Original title i.e title, Overview, Cast and Crew.

Check if there is any missing data in the dataset and duplication of data.

Now we will make another dataset with the columns 'movie_id', 'title', 'tags' and for tags column we will add four columns 'overview', 'genres', 'keywords', 'cast' and 'crew' and the information in these columns would be weird so we need to convert it into proper format. The 'tags' column will be the concantenation of overview, genres, cast, crew, keywords.

At last we're gonna find similarities between the tags of two movies to ultimately recommend that to the end user. For this we use vectorization approach by converting the text into the vectors and this process is called text vectorization. 'Bag of Words' is the technique that we'll use in text vectorization. Every movie is converted into a vector. Now we have to calculate the distance(Cosine distance i.e angle between vectors) from one movie(vector) to the other movie(vector). The more the distance, the less the similarity and vice versa.

When the similarities are known, we made a recommend() function which takes the title of the movie and the similarity function as input.
