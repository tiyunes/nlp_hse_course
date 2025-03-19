
## Results on the test data:

| model                                | public f1-score on kaggle test dataset |
|--------------------------------------|----------------------------------|
| logistic regression (TF-IDF)         | 0.78945                          |
| LSTM (bidirectional, trained from scratch)    | 0.76248                          |
| Transformer (trained from scratch)   | 0.71897                          |
| DistilBERT (fine-tuned)              | 0.82224                          |



## Conclusions:

* The best model in terms of quality was the fine-tuned DistillBERT that demonstrated 0.82224 F1-score on the public part of the test dataset but that was the most biggest model in terms of parameters (overall number of parameters = 66.955.010)

* The best model in terms of balance between complexity and quality was the logistic regression model based on TF-IDF vector representations that shows f1 = 0.78945 on the public part of the test dataset but requires much less amount of parameters

- **How can the achieved results be improved?**
  
  * more extensive hyperparameter tuning for neural networks models trained from scratch
    
  * exploring ensemble models
  * utilizing transfer learning from models trained on similar domains
  * fine-tuning with advanced optimization techniques
- **What difficulties were met?**
  
  * training deep models from scratch required substantial computational resources

  * diverse preprocessing variations were significant challenge

