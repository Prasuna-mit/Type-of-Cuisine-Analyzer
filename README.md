# Analyzer

The tool we are going to implement in this project is an Analyzer. This project is related to prediction of type of cusine by taking the ingredients as input. 

## Getting Started

For this project, the dataset by yummly.com has been taken. This dataset is json format and have the list of dictionaries with three main keys and corresponding values. This project actually helps in setting menu better by predicting relevant cuisines based on the available ingredients.

### Prerequisites

Having a good understanding of python and hands on experience on working with python packages and libraries help a lot.

### Installing

It is a simple yet interesting project. I implemeted this tool on python in jupyter platform. You can use other platforms like pyCharm or can work on terminal aswell. But make sure to install python latest version.

### Explanation

## Data

You can download the dataset from the below website

```https://www.dropbox.com/s/f0tduqyvgfuin3l/yummly.json```

## Data Format
```{
  "id": 10276,
  "cuisine": "mexican",
  "ingredients": [
    "chili powder",
    "crushed red pepper flakes",
    "garlic powder",
    "sea salt",
    "ground cumin",
    "onion powder",
    "dried oregano",
    "ground black pepper",
    "paprika"
  ]
}
```

## Steps to Implement

Data Preprocessing and Feature Extraction:

The most important part for text mining is data curation. This is the fundamental step to achieve more accurate result. Considering this, I have preprocessed the data to check if there are any unwanted data present in the dataset. I have performed ```tokenization, stopwords removal, stemming, removing special characters, etc.``` to prepare for the feature extraction.

Selection of text feature item is a basic and important matter for text mining and information retrieval. Some applications deal with huge amount of text to perform classification or translation and involves a lot of work on the back end. Transforming text into something an algorithm can digest is a complicated process. For feature extraction, I have used TF-IDF (Term Frequenct and Inverse Document Frequency) technique. Which is quite popular technique escpecially works effectively when dealing with large scale of data and in fact, this is one of the reasons behind choosing this technique to get features. 

10 pts: What classifiers/clustering methods did you choose and why?
Modeling: 

The k-nearest neighbors’ technique is based upon the principle that the samples which are similar to each other will lie in close proximity. Given a sample, Knearest neighbor classifier will search the pattern space for k-objects that are closest to it and will delegate the class by identifying the class label which is frequently used. The main advantage of using this algorithm is it is robust to noisy data and works well with the data having many labels. For our large set of data, this method opt perfectly. Apart from that, we require similarity value, and it is one of the advantages of kNN. Therefore, I stick with this algorithm. 

N-Value Selection:

I have chosen N = 10 for clustering. This is not taken randomly. I have evaluated the performace using ```accuracy_score()``` method to check how the model performs with the given number of clusters. I have tuned the method by changing the number of clusters. I found at N = 10, my model performed well with ```accuracy=0.74``` which is quite reasonable acceptance value. However, for N=11,12 the model's performace is almost similat to that of N=10.

Code/ function description:

In brief, I have first gathered the data, preprocessed the data and extratect the text. Perform more text mining and organize the data to use it for vectorization. Vectorized the data to use for the prediction. Divided the dataset into train (75%) and test(25%) data. Built the model using kNN unsupervised algorithm and predicted the values for the test data. Calculated the performance of the model. 


## Running the tests

To test the predicted model, I have taken a list of ingredients and stored into the variable. Vectorized and transformed the set and passed as a parameter to the built model to predict the cuisine. I actually chose random ingredients related to italian cuisine. The model has predicted the same. Additionally, the similarity matrix has also been found to retrieve top "n" (5 in this case) similar cuisine IDs and the distance. Then displayed the top retrieved data.


## Bugs and Assumptions

1. Input must be passed as a variable in the code. 

2. 


## References
1. https://www.uplevel.work/blog

2. https://docs.scipy.org/

3. GeeksforGeeks

4. StackOverflow

## Authors

* **Prasuna Mitikiri** - *prasuna.mitikiri@ou.edu* 

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Inspired by kaggle competition 

