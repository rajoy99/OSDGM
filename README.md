<img src="https://github.com/rajoy99/osman/blob/main/OsmanLogo.png" width="200" height="100" /> 

---

**osman**: A pip package which oversamples class imbalanced binary data by Deep Generative Models.


 

This package offers two APIs. 

1) Variational Auto Encoders 

2) WGAN-GP

**Usage Guide**
---

Installation:

```python
pip install osman
```

The APIs are very simple to use. This example shows the usage of the VAE 

```python
# Applying variational auto encoder on class imbalanced data 
from osman.oversampler import VAEify 

X_vae,y_vae=VAEify(X_train,y_train)

logreg.fit(X_vae,y_vae)

y_pred_vae=logreg.predict(X_test)

score_vae=roc_auc_score(y_pred_vae,y_test)


```
This example shows the usage of the WGAN-GP

```python

from osman.oversampler import WGANify

X_wgan,y_wgan=WGANify(X_train,y_train)

logreg.fit(X_wgan,y_wgan)

y_pred_wgan=logreg.predict(X_test)

score_wgan=roc_auc_score(y_pred_wgan,y_test)
```

Furthermore, consult the tutorial ipython notebook to see the usage on real world credit default dataset.

**Results**

Results on UCI Credit Default dataset with Logistic Regression Classifier.

| Data  | ROC AUC Score |
| ------------- | ------------- |
| Original Imbalanced data | ~38%  |
| Oversampled by osman's VAE API  | ~55%  |
| Oversampled by osman's WGAN-GP API | ~50%  |




**Acknowledgement:**
1) https://arxiv.org/abs/1312.6114
2) https://arxiv.org/abs/2008.09202  
3) https://github.com/justinengelmann/GANbasedOversampling
