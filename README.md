# Adversarial-Attacks-Pytorch

This is a lightweight repository of adversarial attacks for Pytorch.
There are frequently used attacks methods and some utils.
The aim is to provide use adversarial images wihout bothering.

## Usage

### Dependencies

- torch 1.2.0
- python 3.6

### Installation

- `pip install torchattacks` or
- `git clone https://github.com/HarryK24/adversairal-attacks-pytorch`

```python
import torchattacks
pgd_attack = torchattacks.PGD(model, eps = 4/255, alpha = 8/255)
adversarial_images = pgd_attack(images, labels)
```

### Precautions

WARNING :: All images should be scaled to [0, 1] with transform[to.Tensor()] before used in attacks.
WARNING :: All models should return ONLY ONE vector of `(N, C)` where `C = number of classes`.

### Attacks and Papers

The papers and the methods that suggested in each article with a brief summary and example.
All methods in this repository are provided as *CLASS*, but methods in each Repo are *NOT CLASS*.

* **Explaining and harnessing adversarial examples** : [Paper](https://arxiv.org/abs/1412.6572), [Repo](https://github.com/HarryK24/FGSM-pytorch)
  - FGSM

* **Adversarial Examples in the Physical World** : [Paper](https://arxiv.org/abs/1607.02533), [Repo](https://github.com/HarryK24/AEPW-pytorch)
  - IFGSM
  - IterLL

* **Ensemble Adversarial Traning : Attacks and Defences** : [Paper](https://arxiv.org/abs/1705.07204), [Repo](https://github.com/HarryK24/RFGSM-pytorch)
  - RFGSM

* **Towards Evaluating the Robustness of Neural Networks** : [Paper](https://arxiv.org/abs/1608.04644), [Repo](https://github.com/HarryK24/CW-pytorch)
  - CW(L2)

* **Towards Deep Learning Models Resistant to Adversarial Attacks** : [Paper](https://arxiv.org/abs/1706.06083), [Repo](https://github.com/HarryK24/PGD-pytorch)
  - PGD

* **Comment on "Adv-BNN: Improved Adversarial Defense through Robust Bayesian Neural Network"** : [Paper](https://arxiv.org/abs/1907.00895)
  - APGD

### Demos

* **White Box Attack with Imagenet** ([code](demos/White%20Box%20Attack%20with%20Imagenet.ipynb)): 
This demo make adversarial examples with the Imagenet data to fool [Inception v3](https://arxiv.org/abs/1512.00567). However, whole Imagenet data is too large so in this demo, so it uses only '[Giant Panda](http://www.image-net.org/)'. But users are free to add other images in the Imagenet data. 

* **Black Box Attack with CIFAR10** ([code](demos/Adversairal%20Training%20with%20MNIST.ipynb)): 
In this demo, there is a black box attack example with two different models. First, make adversarial datasets from a holdout model with CIFAR10. Second, use the datasets to attack a target model. An accuracy dropped from 77.77% to 5.1%. Also this code also contains 'Save & Load' example.

* **Adversairal Training with MNIST** ([code](demos/Adversairal%20Training%20with%20MNIST.ipynb)): 
This demo shows how to do adversarial training with this repository. MNIST and custom model are used in this code. The adversarial training is progressed with PGD Attack, and FGSM Attack is applied to test the model. An accuracy of normal images is 96.37% and an accuracy of FGSM attack is 96.11% .


## Update Records

### ~ Version 0.3

* FGSM, IFGSM, IterLL, RFGSM, CW(LW), PGD added.
* Demos uploaded.

### Version 0.4

* package name 'attacks' changed to 'torchattacks'.
* APGD attack added.
* update_model method added.