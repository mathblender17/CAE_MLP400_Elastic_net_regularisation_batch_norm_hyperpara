# CAE_MLP400_Elastic_net_regularisation_batch_norm_hyperparameters
## Here I try Elastic Net regularisation in the last layer With batch normalisation

### **Elastic Net Regularisation**
- Elastic Net regularization is a combination of L1 regularization (Lasso) and L2 regularization (Ridge) techniques. It is designed to address some of the limitations of each individual regularization method. Both L1 and L2 regularization involve adding penalty terms to the loss function to prevent overfitting and encourage the model to generalize well to new, unseen data.


### **Batch Normalisation** 
- smooths the loss function
- Batch Normalization helps to ensure that the inputs to each layer in a neural network have a consistent distribution, which can lead to faster and more stable training. It has been shown to have regularization effects, allowing for the use of higher learning rates and potentially reducing the need for other regularization techniques.
- ####  **Benefits:**
    - Improved stability during training: BN helps in maintaining a more stable distribution of activations.
    - Faster convergence: It can allow for the use of higher learning rates and, in some cases, reduce the need for other regularization techniques.
    - Acts as a regularizer: The normalization process can have a regularizing effect on the model.


### In summary, normalization is about scaling input features, while Batch Normalization is about normalizing layer activations within the neural network during training. Batch Normalization offers benefits such as improved training stability, faster convergence, and some inherent regularization effects, making it a widely used technique in deep learning architectures.

**In machine learning, hyperparameters are settings that control the learning process of a model, but their values are not learned by the model itself. They are set by the user before training begins and remain constant throughout the training process. Essentially, they are like knobs you turn to adjust the behavior of your learning algorithm.**

## Results:
**APPROACH 1: Elastic regularisation applied indirectly & Grid Search for hyper parameters** ***only l1 used***
```
# Downloading data from https://www.cs.toronto.edu/~kriz/cifar-10-python.tar.gz
170498071/170498071 [==============================] - 2s 0us/step
1563/1563 [==============================] - 7s 3ms/step
313/313 [==============================] - 1s 4ms/step
Batch Size: 8, Learning Rate: 0.001, Test Accuracy: 0.2378
Batch Size: 8, Learning Rate: 0.01, Test Accuracy: 0.2418
Batch Size: 16, Learning Rate: 0.001, Test Accuracy: 0.2594
Batch Size: 16, Learning Rate: 0.01, Test Accuracy: 0.2388
Batch Size: 32, Learning Rate: 0.001, Test Accuracy: 0.2368
Batch Size: 32, Learning Rate: 0.01, Test Accuracy: 0.2548
Batch Size: 64, Learning Rate: 0.001, Test Accuracy: 0.0969
Batch Size: 64, Learning Rate: 0.01, Test Accuracy: 0.2800
Best Accuracy: 0.2800 with Batch Size: 64, Learning Rate: 0.01
```

**Approach 2 :  *l1 and l2 both used***
```
 Best Accuracy: 0.3917 with Batch Size: 64, Learning Rate: 0.001
```
### Grid search is a systematic method, but it can be computationally expensive, especially when dealing with a large number of hyperparameters and their possible values.
***Approach 3:Bayesian*** 
```
1563/1563 [==============================] - 17s 10ms/step
313/313 [==============================] - 3s 10ms/step
100%|██████████| 20/20 [38:45<00:00, 116.29s/trial, best loss: -0.26100000739097595]
Best hyperparameters: Batch Size: 32, Learning Rate: 0.009360527227641056, Alpha: 0.6919125492039278, Rho: 0.18166965893871023
```

***Approach 4:Bayesian ( with more polishing)*** 
```
# 100%|██████████| 20/20 [44:06<00:00, 132.30s/trial, best loss: -0.28060001134872437]
Best hyperparameters: Batch Size: 64, Learning Rate: 0.01763211249105561, Alpha: 0.8638905622827661, Rho: 0.11757792046491378
```



