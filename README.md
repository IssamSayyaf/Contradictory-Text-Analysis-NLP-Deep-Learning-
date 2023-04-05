# Contradictory-Text-Analysis-NLP-Deep-Learning-
**This project done by Ahmad Mahmod and I (Mohamad Issam Sayyaf).**


We are conducting a classification task on pairs of sentences, which consist of a premise and a hypothesis. The task involves categorizing each pair into one of three categories - entailment, contradiction, or neutral.

To illustrate this, let's consider an example using the following premise:

"He came, he opened the door and I remember looking back and seeing the expression on his face, and I could tell that he was disappointed."

For the first hypothesis,

"Just by the look on his face when he came through the door I just knew that he was let down,"

we can infer that it is true based on the information in the premise. Therefore, this pair is related by entailment.

For the second hypothesis,

"He was trying not to make us feel guilty but we knew we had caused him trouble,"

we cannot reach a conclusion based on the information in the premise. Thus, this relationship is neutral.

For the third hypothesis,

"He was so excited and bursting with joy that he practically knocked the door off its frame,"

we know that it is untrue as it contradicts the information in the premise. Hence, this pair is related by contradiction.

The dataset contains premise-hypothesis pairs in fifteen different languages, namely Arabic, Bulgarian, Chinese, German, Greek, English, Spanish, French, Hindi, Russian, Swahili, Thai, Turkish, Urdu, and Vietnamese. We are interested only with the English pairs.


<p align="center">
  <img src="https://drive.google.com/uc?id=1-LX56EaueXtVfO6tC75LRD4OhrMmelqW" alt="alt text" width="width" height="height" />
  <br>
  <em>The Dataset Distribution</em>
</p>

Dataset Descriptions:
The dataset provided for Task 2 of the Contradictory Text Analysis competition is a crucial component of the competition. In this task, the dataset contains different couples of sentences (a premise and a hypothesis) in different languages. Each couple has a label of one out of three classes:

- Entailment: the two sentences a related in meaning
- Neutral: the sentences are neither related nor contraries
- Contradiction: the sentences are contraries in meaning
The data set contains two csv files:

- train.csv: This file contains the ID, premise, hypothesis, and label, as well as the language of the text and its two-letter abbreviation
- test.csv: This file contains the ID, premise, hypothesis, language, and language abbreviation, without labels.

The dataset contains a considerable number of samples, among which English samples represent a dominant portion of 56.7% as shown in Figure 12. The Task will develop a model, which will classify only English sentences couples in one of the mentioned classes.

For the English language, the distribution of the three classes in the dataset is nearly uniform, indicating that there is a balanced representation of sentence pairs labeled as Entailment, Neutral, and Contradiction. This suggests that the dataset provides a fair representation of the relationship between sentence pairs in the English language and can be effectively used to train models for the task of Contradictory Text Analysis in this language as shown in Figure 13.

