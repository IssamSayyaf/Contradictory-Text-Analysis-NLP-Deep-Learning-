# Contradictory-Text-Analysis-NLP-Deep-Learning-
**This project done by Ahmad Mahmod and I (Mohamad Issam Sayyaf).**


 We are conducting a classification task on pairs of sentences, which consist of a premise and a hypothesis. The task involves categorizing each pair into one of three categories - entailment, contradiction, or neutral. To illustrate this, let's consider an example using the following premise:

**"He came, he opened the door and I remember looking back and seeing the expression on his face, and I could tell that he was disappointed."**

For the first hypothesis,

**"Just by the look on his face when he came through the door I just knew that he was let down,"**

we can infer that it is true based on the information in the premise. Therefore, this pair is related by entailment.

For the second hypothesis,

**"He was trying not to make us feel guilty but we knew we had caused him trouble,"**

we cannot reach a conclusion based on the information in the premise. Thus, this relationship is neutral.

For the third hypothesis,

**"He was so excited and bursting with joy that he practically knocked the door off its frame,"**

we know that it is untrue as it contradicts the information in the premise. Hence, this pair is related by contradiction.

The dataset contains premise-hypothesis pairs in fifteen different languages, namely Arabic, Bulgarian, Chinese, German, Greek, English, Spanish, French, Hindi, Russian, Swahili, Thai, Turkish, Urdu, and Vietnamese. We are interested only with the English pairs.


<p align="center">
  <img src="https://github.com/IssamSayyaf/Contradictory-Text-Analysis-NLP-Deep-Learning-/blob/main/images/New%20Bitmap%20Image.bmp" alt="alt text" width="width" height="height" />
  <br>
  <em>Figure 1: The Dataset Distribution</em>
</p>

Dataset Descriptions:
The dataset provided for Task 2 of the Contradictory Text Analysis competition is a crucial component of the competition. In this task, the dataset contains different couples of sentences (a premise and a hypothesis) in different languages. Each couple has a label of one out of three classes:

- Entailment: the two sentences a related in meaning.
- Neutral: the sentences are neither related nor contraries.
- Contradiction: the sentences are contraries in meaning.

The data set contains two csv files:

- train.csv: This file contains the ID, premise, hypothesis, and label, as well as the language of the text and its two-letter abbreviation
- test.csv: This file contains the ID, premise, hypothesis, language, and language abbreviation, without labels.

The dataset contains a considerable number of samples, among which English samples represent a dominant portion of 56.7% as shown in Figure 1. The Task will develop a model, which will classify only English sentences couples in one of the mentioned classes.

For the English language, the distribution of the three classes in the dataset is nearly uniform, indicating that there is a balanced representation of sentence pairs labeled as Entailment, Neutral, and Contradiction. This suggests that the dataset provides a fair representation of the relationship between sentence pairs in the English language and can be effectively used to train models for the task of Contradictory Text Analysis in this language as shown in Figure 2.

<p align="center">
  <img src="https://drive.google.com/uc?id=1-MWiR2zllSEPMTS2txhmyz8PJmUb29TE" alt="alt text" width="width" height="height" />
  <br>
  <em>Figure 2: The distribution every class in English Language</em>
</p>


We have computed some statistical information on the samples in terms of the number of characters present in them. Specifically, we have calculated the mean, standard deviation, and count of characters across all the samples in the dataset as shown in Figure 3.
The mean of characters across all samples provides a measure of the central tendency of the dataset and indicates the typical length of the samples. The standard deviation of characters provides a measure of the dispersion of the data around the mean and indicates how much the lengths of the samples vary from the typical length. The count of characters provides information on the total number of characters present in the dataset.


<p align="center">
  <img src="https://drive.google.com/uc?id=1-N5O45jUOpQHNOOM0ePDyyy4BnNnPwFX" alt="alt text" width="width" height="height" />
  <br>
  <em>Figure 3: The statistical study for the dataset.</em>
</p>
These statistics can be useful in understanding the properties of the dataset and in developing models that can handle samples of different lengths effectively. For instance, models that are sensitive to the length of the samples may require additional preprocessing or architecture modifications to handle samples with varying lengths effectively. Overall, the statistical information on the number of characters in the dataset can provide valuable insights for developing effective models for Contradictory Text Analysis. 
 
# Methods
To design an efficient model for Contradictory Text Analysis, we establish a pipeline that consists of the following steps:
## Preprocessing

To design an efficient model for Contradictory Text Analysis, we establish a pipeline that consists of the following steps:

1. **Read the dataset**:
Load the dataset from a CSV file and store it in a panda DataFrame.

2. **Extract English Sentences**:
Extract English sentences from the train and test datasets based on the language's two-letter abbreviation label provided in the CSV files. This will result in a sample size of 6869 sentences for training.

3. **Split the Dataset**:
Split the data into training, validation, and test sets with 70%, 25%, and 5% of the data, respectively.

4. **Tokenize the text**:
In natural language processing (NLP), a tokenizer is a tool that splits text into smaller chunks called tokens. These tokens can be individual words or groups of words that are meaningful together, such as named entities or phrases.

   We use the Tokenizer class provided by TensorFlow's Keras API as a text-preprocessing tool. It converts text into sequences of integers that can be fed into a neural network for further processing.

By following this preprocessing pipeline, we can prepare the Contradictory Text Analysis dataset and proceed with designing and training the model architecture. After training, we can evaluate the performance of the model on the dataset. We use RobertaTokenizer which is a tokenizer class provided by the Hugging Face Transformers library, is used to convert text data into numerical sequences that can be fed into a deep learning model such as BERT, RoBERTa, or other transformer-based models. It is specifically designed to work with the RoBERTa model architecture and is based on the Byte-Pair Encoding (BPE) algorithm.
The tokenizer concatenates both premise and hypothesis sentences and tokenizes them together enabling both truncation and padding of the input sequences to ensure that they have the same length.
This code creates a Dataset object from the training encodings and labels. It first creates a tuple of (input_ids, attention_mask) dictionary and the corresponding labels. Finally, the batch method batches the dataset with a specified batch size BATCH_SIZE. The resulting train_dataset and val_dataset is a TensorFlow dataset object that can be used for training the model.

# Designing and Training the Model Architecture

The model architecture uses the RoBERTa language model, which is a state-of-the-art language model based on the Transformer architecture. It is an improvement over the original BERT model, developed by Facebook AI in 2019, and has shown better generalization and higher performance on downstream NLP tasks.

The RoBERTa model uses the same architecture as BERT as shown in Figure 4, consisting of an encoder composed of several Transformer blocks. Each Transformer block consists of a self-attention mechanism and a feedforward neural network.

The key innovation in the Transformer architecture is the self-attention mechanism, which allows the model to weigh the importance of different words in a sequence when generating the output. The self-attention mechanism is applied to both the input (encoder) and output (decoder) sequences, allowing the model to take into account the entire context of the input sequence when generating the output.

<p align="center">
  <img src="https://github.com/IssamSayyaf/Contradictory-Text-Analysis-NLP-Deep-Learning-/blob/main/images/The%20architecture%20RoBERTa%20model.png" alt="alt text" width="width" height="height" />
  <br>
  <em>Figure 4: The Architecture of the proposed model.</em>
</p>





