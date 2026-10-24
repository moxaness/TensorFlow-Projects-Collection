# TensorFlow Projects Collection

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-D00000?logo=keras&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=white)

Deep-learning notebooks built with **TensorFlow 2 / Keras** while learning neural networks, from the standard MNIST exercise to a business-oriented classification problem.

| Notebook | Problem | Model | Test accuracy |
|---|---|---|---|
| [`MNIST.ipynb`](MNIST.ipynb) | Recognise handwritten digits (0–9) from 28×28 images | Fully-connected network, 2 hidden layers × 50 units, Adam, sparse categorical cross-entropy | **97.3 %** |
| [`BUSINESS_CASE.ipynb`](BUSINESS_CASE.ipynb) | Predict whether an audiobook-app customer will **buy again**, so marketing can target the customers likely to return | Fully-connected network on 10 customer features, with **early stopping** to prevent overfitting | **91.1 %** |

---

## MNIST – handwritten digit classification

- Load MNIST with `tensorflow-datasets`, scale pixels to [0, 1], and split off a validation set from the training data
- Shuffle and batch the data with the `tf.data` pipeline
- Train a dense network for 5 epochs: validation accuracy reaches 97.9 %, and accuracy on the held-out test set is 97.3 %

## Business case – audiobook customer retention

- Input: 10 per-customer features covering 2 years of activity (book lengths, prices paid, reviews, minutes listened, completion rate, support requests, days between purchase and last visit)
- Target: whether the customer makes another purchase within the next 6 months
- Data comes pre-split into train / validation / test `.npz` files
- Training with `EarlyStopping` on the validation loss, then evaluation on the test set

> The `Audiobooks_data_*.npz` files the second notebook expects aren't included in the repository.

## How to run

```bash
pip install tensorflow tensorflow-datasets numpy jupyter
jupyter notebook
```

## Author

**Mohammed Anes Boucetla** – [github.com/moxaness](https://github.com/moxaness)
