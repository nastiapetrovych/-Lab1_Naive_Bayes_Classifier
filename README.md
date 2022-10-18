# Lab1_Naive_Bayes_Classifier
The group project of testing Naive Bayes formula based on R


The aim of the lab was to test the Naive Bayes formula, which indicates probabillity of event.

![image](https://user-images.githubusercontent.com/92577132/196523000-44c6aae7-f886-4daa-a611-338167eee9ed.png)

Firstly, we had the database of words on which we should train our model and indicates the probability that the given world is fake or credible.

Given this info, we got the table of the word, its numbers of occurences and counted the probability as number of given words in credible or fake dataframe devided by number of all words in credible or fake dataframe.

After it, when we receive our new csv file, we read it and from each sentence form the bag of words. Each word recursively calls the function which count its probability of being fake or credible. Then, according to the bag of words model, we multiply the probability for each word in the sentence and compare which one is bigger. The given model efficiently detects whether the sentence is credible. The accurancy is more than 80%. Some percentage of mistake can be caused by avoiding the order of words(it is the reason why it is a Naive) and also we omit words which aren't in our training model. 


# Probability and Statistics

# Lab Assignment 1: Naive Bayes Classifier

### *Tymur Krasnianskyi, Olha Hahurna, Anastasiia Petrovych*

## Introduction

During the past three weeks, we learned a couple of essential notions
and theorems, and one of the most important among them is the *Bayes
theorem*.

One of its applications is **Naive Bayes classifier**, which is a
probabilistic classifier whose aim is to determine which class some
observation probably belongs to by using the Bayes formula:
$$\mathsf{P}(\mathrm{class}\mid \mathrm{observation})=\frac{\mathsf{P}(\mathrm{observation}\mid\mathrm{class})\mathsf{P}(\mathrm{class})}{\mathsf{P}(\mathrm{observation})}$$

Under the strong independence assumption, one can calculate
$\mathsf{P}(\mathrm{observation} \mid \mathrm{class})$ as
$$\mathsf{P}(\mathrm{observation}) = \prod_{i=1}^{n} \mathsf{P}(\mathrm{feature}_i), \qquad \mathsf{P}(\mathrm{observation} \mid \mathrm{class}) = \prod_{i=1}^{n} \mathsf{P}(\mathrm{feature}_i \mid \mathrm{class}),$$
where $n$ is the total number of features describing a given
observation. Thus, $\mathsf{P}(\mathrm{class}|\mathrm{observation})$ now
can be calculated as

$$\mathsf{P}(\mathrm{class} \mid \mathrm{\mathrm{observation}}) = \mathsf{P}(\mathrm{class})\times \prod_{i=1}^{n}\frac{\mathsf{P}(\mathrm{feature}_i\mid \mathrm{class})}{\mathsf{P}(\mathrm{feature}_i)}\tag{1}$$

## Data description

-   **2 - fake news** This data set contains data of American news: a
    headline and an abstract of the article. Each piece of news is
    classified as fake or credible. The task is to classify the news
    from test.csv as credible or fake.
