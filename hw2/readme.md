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

* notebook: notebooks/hw2_nlp_ngram.ipynb
# LSTM model

I've conducted several experiments with LSTM model.
The best setting was LSTM with encoder-decoder-like architecture with approximately 8 millions of trainable parameters. The encoder–decoder LSTM uses 128 token embedding size and 128 hidden state dimension. Both the encoder and decoder are single‐layer LSTMs: the encoder is bidirectional and the decoder is a unidirectional 128-hidden LSTM. 

Results of the best LSTM model:
| model                                | average perplexity on correct examples|  average perplexity on incorrect examples|
|--------------------------------------|----------------------------------|----------------------------------|
| LSTM        | 11578.11                          | 21359.99                         |

* notebook: notebooks/hw2_nlp_lstm.ipynb
# Fine-tuned model

For fine-tuning I've used DistilGPT2, a 6-layer decoder-only Transformer distilled from GPT-2 small, with 768-dimensional hidden states, 12 self-attention heads per layer, and a causal masking setup. It was originally pretrained on the OpenWebText corpus under the supervision of GPT-2 model, yielding approximately 82 million trainable parameters. 

Results of the fine-tuned model:
| model                                | average perplexity on correct examples|  average perplexity on incorrect examples|
|--------------------------------------|----------------------------------|----------------------------------|
| fine-tuned model        | 240.92                          | 6545.1                         |

* notebook: notebooks/hw2_nlp_finetuning.ipynb
# Conclusion 

* The best model in terms of quality was the fine-tuned DistilGPT2, achieving an average perplexity of 241 on correct phrases but it’s also the largest model with approx. 82 million trainable parameters.

* The best model in terms of efficiency was the 3-gram baseline: while its perplexity is much higher, it requires minimal memory.

- **How can the achieved results be improved?**
  - Use adapter/LoRA methods to further fine-tune DistilGPT2 with less compute.
  - Tune the hyperparameters for LSTM model

- **What difficulties were met?**
  - The main difficulty was training neural network from scratch as it requires a lot of compute and it is sensitive to learning rate

