# chatbot_movie_conversation
This repo is about the chatbot model with seq2seq. <br>
<em><b>Dataset</b></em>: The dataset is cornell movie-dialogs corpus, which contains 220,579 conversational exchanges between 10,292 pairs of movie characters, 9,035 characters from 617 movies with various genres. <br>
       Two txt files in the dataset:<br>
       1. movie_lines: with all the single sentence of moives. It has four fields:"lineID", "characterID", "movieID", "character", "text" <br>
       2. movie_conversation: with paired conversation. It has four fields: "character1ID", "character2ID", "movieID", "utteranceIDs". utteranceID is the sequential lineID to form conversations. <br>
       
<b>Dataloader</b>:
To format the new csv file with ID and sequential utterances. <br>
Embedding: Bag-of-Word
Max_length =10<br>
min_count = 2 <br>
After processing, the corpus is trimmed to 53165 sentence pairs.<br>

<em><b>Encoder</b> </em>: GRU, Luong attention<br>
<em><b>Batch size</b> </em>: 128<br>
<em><b>Learning rate</b> </em>:0.0001
<em><b>Best epoch</b> </em>: 32, with total 50 epochs<br>
<em><b>Loss</b> </em>: cross entropy loss implements based on Sahannon Probability<br>
<em><b>Novelty</b> </em>: <br>
         more steps in data preprocessing<br>
         adjust the max length of sentences<br>
         adjust teacher force ratio<br>
         reduce hidden layers <br>
         save and load best model<br> 
<em><b>Visualization</b> </em>of the loss:<br>
<img align='center' style="border-color:gray;border-width:2px;border-style:dashed"  src="loss.png" width = "600px" height="300px" ></img>

<em><b>Visualization</b> </em>of the result:<br>
<img align='center' style="border-color:gray;border-width:2px;border-style:dashed"  src="example.png" width = "300px" height="300px" ></img>
