# NLP_IMDB_reviews

Building a Natural Language Process model by using IMDB_reviews_dataset 

## The purpose of the code:

* To practice the skills I have earned in Natural Lnguage Process as a branch of time_series field
* Build a NLP model step by step


## Preparing the data

### Loading the dataset
In this code we use a dataset from `Tensorflow_datasets` called `IMDB_reviews`, which contains *25000* movie reviews. To use this dataset, we first import the libraries we need:
`tensorflow` and `tensorflow_datasets`

Then  we load the datasets from tensorflow_datsets by using the code bellow:


`imdb, info = tfds.load("imdb_reviews", with_info= True, as_supervised=True)`

And split the data to a **train_set** and a **test_set**. Next we use a `for` loop to iterate over the train_set and extract the sentences of movie reviews and their labels from it and add them in list seperately, a list for the sentences and a list for the labels as it is shown in the following code:

```
train_sentences = []
train_labels = []

for s, l in train_set :
  train_sentences.append(s.numpy().decode('utf8'))
  train_labels.append(l.numpy())
  ```
  We do the same thing for the test_set as well, then conver these list to numpy arrays for convinience.

```
train_sentences = np.array(train_sentences)
test_sentences = np.array(test_sentences)
train_labels = np.array(train_labels)
test_labels = np.array(test_labels)
```

