## Dataset 

I've chosen the sports, tech, and business categories from [BBC news dataset](https://www.kaggle.com/datasets/pariza/bbc-news-summary), which together comprise 1422 news articles.

Description of the dataset: this dataset was created using a dataset used for data categorization that consists of 2225 documents from the BBC news website corresponding to stories in five topical areas from 2004-2005 used in the paper of D. Greene and P. Cunningham. "Practical Solutions to the Problem of Diagonal Dominance in Kernel Document Clustering", Proc. ICML 2006; whose all rights, including copyright, in the content of the original articles are owned by the BBC.

Average number of words in news dataset = 378.03


# N-gram model
The main parameter n=3 and words that occur less frequently than 3 are not considered part of the vocabulary. 

Results of the 3-gram model:
| model                                | average perplexity on correct examples|  average perplexity on incorrect examples|
|--------------------------------------|----------------------------------|----------------------------------|
| 3-gram model        | 8206.71                          | 9853.56                         |

# LSTM model

I've conducted several experiments with LSTM model
The best setting was LSTM with encoder-decoder-like architecture with approximately 8 millions of trainable parameters

Results of the best LSTM model:
| model                                | average perplexity on correct examples|  average perplexity on incorrect examples|
|--------------------------------------|----------------------------------|----------------------------------|
| LSTM        | 11578.11                          | 21359.99                         |


# Fine-tuned model
