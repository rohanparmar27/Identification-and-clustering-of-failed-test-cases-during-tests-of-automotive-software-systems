# Identification-and-clustering-of-failed-test-cases-during-tests-of-automotive-software-systems
A massive volume of system failure data is generated during testing. Manual analysis of this data is time-consuming and requires specialized expertise. There is a need for an automated, efficient, and accurate method to analyze system failures.
# Methodology
- Therer are three phase of the mathodology, data collectiion and preprocessing,model training and validation and last phase failure analysis. In first phase here i used dataset based on of the autonomous car disengagement details as well as the test report of hil.
- The both data firstly preprocessed. In preprocess of text data Text preprocessing removes special characters and digits from the text data. Further, the text is tokenized into individual words. It removes common words that do not contribute to the meaning of the data using the stopwords list from NLTK. The Snowball Stemmer is then used to reduce words to their base formThe text is vectorized using the Keras Tokenizer to make sequences of integers, and such sequences are then pre-padded up to a maximum length of 48 to give the input in a standard size. The sequences are further normalized to put the data into a scaled range. Finally, the preprocessed data will be reshaped to fit the input of the CAE. The data is split into a ratio of 80-10-10 for training, validation, and testing to carry out an evaluation that is complete and balanced. 
- The CAE is used to process the training data and encode it. The CAE is composed of an encoder, which compresses the input data to a lower-dimensional latent space, and a decoder, which reconstructs the input from this space. In that process, essential features and patterns in the data are captured, and thus efficient and effective analysis of data becomes possible. The CAE is particularly suited for handling structured data and thus is helpful in the case of unstructured text data to have reliable extraction of features. The encoder part of the CAE is used once the CAE is trained to extract the encoded features from the training, validation, and labeled data.
- K-Means is applied over the encoded features to group similar failure patterns. For testing, the trained CAE encoder and the best K-Means clustering model are loaded. The labeled data is encoded with the CAE, and clusters are predicted with the K-Means model. In addition, external text data for HIL test reports is analyzed. The same preprocessing, tokenization, and encoding steps are done for this data as for the original dataset. The clusters that are predicted from the external data are mapped to their respective failure types, and the results are presented to demonstrate how the model can be used to predict failure types from new, unseen data.
![image](https://github.com/user-attachments/assets/e7078389-de84-48fe-840d-bd74fe71921a)
# Workflow
![image](https://github.com/user-attachments/assets/03ce13b6-674b-4753-9957-455592ebf51d)
# Hyperparameter Optimization Results
![image](https://github.com/user-attachments/assets/af47e267-5918-4b66-b0d8-ed503ab46e3d)
- (a) Validation DBI with different number of kernel size and epochs. (b) Validation DBI with different number of Filters and epochs. (c) Validation DBI with different optimizer and learning rates.
#  Hyperparameter tuning tested range and selected values
![Picture3](https://github.com/user-attachments/assets/b8ddcfeb-0104-4ed3-8539-0d8105ddb130)
# Davies-Bouldin Index Score with Different Number of clusters
![image](https://github.com/user-attachments/assets/93f13616-cab2-44f6-841e-c73d79b7a026)
- DBI Score is 0.4754898219990414 for two clusters, 0.48726179118994806 for four clusters, and 0.5111786312928929 for nine clusters
- The DBI is a metric used to evaluate the quality of clustering results, where lower values indicate better clustering. While a DBI of 0.4754898219990414 for two clusters is the lowest, it might be insufficient to capture the complexities of the failure types. Conversely, nine clusters might over-segment the data, leading to less interpretable results. A four-cluster solution might represent a reasonable balance between the desire for a lower DBI and the need to adequately represent different failure types. It might provide a suitable for our analysis. In conclusion, the selection of four clusters is a practical decision based on a combination of DBI scores, domain knowledge, and the desire to find a best solution as 4 class for over and under clustering. In the next slide I explain the comparison of models.
# Autoencoder Model Comparison
![image](https://github.com/user-attachments/assets/a5cb13ca-67aa-4c68-9729-bdcb502d0901)
- Comparision of Autoencoder, LSTM autoencoder, Convolution Autoencoder and Stand Alone Kmeans for the selection of best model for failure analysis
-For analysis comapre MSE for Deep learning Models, Davis Bouldin Index score for K-Means and Accuracy for overall  testing data analysis results.
# Visual representation of cluster
![image](https://github.com/user-attachments/assets/18dbded3-e43e-4e93-9004-ed602b3ca536)
# Results
- Utilized deep learning and clustering methodologies to effectively detect faults in automotive software systems.
- The Convolutional Autoencoder (CAE) was trained for 20 epochs, with a batch size of 128.
- The Adam optimizer was used, and the performance metric was mean squared error.
- Obtained a training mean squared error (MSE) of 0.00549, a validation MSE of 0.00662, and a testing MSE of 0.00686.
- The DBI scores for the validation data and test data were 0.4872 and 0.601, respectively.
- The model's accuracy of 94.4% indicates a good outcome.
# Conclusion
- Research successfully proves the application of deep learning and clustering techniques for failure analysis.
- Convolutional Autoencoder for feature extraction and K-Means clustering for failure grouping, failure were identified and classified with high accuracy.
- The lowest DBI score ensures well-defined fault groupings and high interpretability.
- The results confirm the feasibility and effectiveness of the proposed methodology, improving the reliability and safety of automotive software systems.




