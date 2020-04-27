# Image-Captioning-Project
Image Captioning is the process of generating textual description of the image, here the input is the image and the output is the caption. 

### Dataset
Dataset used for this project is Flickr8k (available on Kaggle), we have used 8k images. Each image has 5 captions describing it.  We will be using 6k images for training , 1k for validation(dev) and 1k for testing.

### Data Collection and Data Cleaning 
Read all the captions from the file. Store the particular image id and all the captions describing it in a dictionary called descriptions. Data cleaning is done for all the captions by removing all the  special characters, small words and converting all the characters into lowercase and finally storing all the captions in new text file descriptions_1.txt

### Vocabulary 
Vocabulary is a set of all possible words our model can predict and vocab is contructed from descriptions_1.txt Storing all the unique words in the vocabulary and then shortening the vocabulary upto some certain threshold for limiting the total no of words on the basis of the frequency count of the words.  

### Data Preprocessing – Images
We are using ResNet50 model for feature extraction from images. Further preprocessing image and encoding the image. Saving the encodings of train and test images in encoded_train_featurs.pkl and encoded_train_features.pkl and whenever we require the data we can load it again with the help of pickle.

### Data Preprocessing – Captions 
Preprocessing all the words in the vocab into features and every feature is represented by numeric values. So, creating two word_to_idx and idx_to_word dictionaries for mapping each word with the value. These dictionaries are saved as idx_to_word.pkl and word_to_idx.pkl for future use.

### Word Embeddings
Mapping every word(index) to a 200-long vector and we will be using pre-trained Glove model. (available as 'glove.6B.200d.txt'). We have created embedding matrix for all the words in our vocabulary. 

### Model Architecture
Finally, Training and Compiling our model and saving it as model_weights/model_9.h5. Moreover, The model has been loaded in Caption_It.ipynb and Image Captions have been predicted. Further we can deploy this model with the help of Flask and basics of HTML and CSS.

References -  (https://towardsdatascience.com/image-captioning-with-keras-teaching-computers-to-describe-pictures-c88a46a311b8)



