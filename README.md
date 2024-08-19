# Identification-and-clustering-of-failed-test-cases-during-tests-of-automotive-software-systems
A massive volume of system failure data is generated during testing. Manual analysis of this data is time-consuming and requires specialized expertise. There is a need for an automated, efficient, and accurate method to analyze system failures.
# Methodology
Therer are three phase of the mathodology, data collectiion and preprocessing,model training and validation and last phase failure analysis. In first phase here i used dataset based on of the autonomous car disengagement details as well as the test report of hil.
The both data firstly preprocessed. In preprocess of text data Text preprocessing removes special characters and digits from the text data. Further, the text is tokenized into individual words. It removes common words that do not contribute to the meaning of the data using the stopwords list from NLTK. The Snowball Stemmer is then used to reduce words to their base formThe text is vectorized using the Keras Tokenizer to make sequences of integers, and such sequences are then pre-padded up to a maximum length of 48 to give the input in a standard size. The sequences are further normalized to put the data into a scaled range. Finally, the preprocessed data will be reshaped to fit the input of the CAE. The data is split into a ratio of 80-10-10 for training, validation, and testing to carry out an evaluation that is complete and balanced. 
The CAE is used to process the training data and encode it. The CAE is composed of an encoder, which compresses the input data to a lower-dimensional latent space, and a decoder, which reconstructs the input from this space. In that process, essential features and patterns in the data are captured, and thus efficient and effective analysis of data becomes possible. The CAE is particularly suited for handling structured data and thus is helpful in the case of unstructured text data to have reliable extraction of features. The encoder part of the CAE is used once the CAE is trained to extract the encoded features from the training, validation, and labeled data.
K-Means is applied over the encoded features to group similar failure patterns. For testing, the trained CAE encoder and the best K-Means clustering model are loaded. The labeled data is encoded with the CAE, and clusters are predicted with the K-Means model. In addition, external text data for HIL test reports is analyzed. The same preprocessing, tokenization, and encoding steps are done for this data as for the original dataset. The clusters that are predicted from the external data are mapped to their respective failure types, and the results are presented to demonstrate how the model can be used to predict failure types from new, unseen data.
![image](https://github.com/user-attachments/assets/e7078389-de84-48fe-840d-bd74fe71921a)
