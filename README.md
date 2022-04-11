# cycle_mnist_dataset
A dataset like mnist but difficult to train with typical CNN

Can you train a machine learning model to use this dataset to identify whether there are cycle in these images?

Like mnist dataset, these images are 28*28 pixels, with 60000 images in training dataset and 10000 images in testing dataset.

![output](https://user-images.githubusercontent.com/68770027/162715593-0ce8bc17-8369-4458-a4c7-a4b023b6292a.png)


## how to load and plot

```python
import numpy as np
import matplotlib.pyplot as plt

cycle_dataset = np.load('cycle_dataset.npz')
train_images = cycle_dataset['train_images']
train_labels = cycle_dataset['train_labels']
test_images = cycle_dataset['test_images']
test_labels = cycle_dataset['test_labels']

plt.figure(figsize=(10,10))
for i in range(25):
    plt.subplot(5,5,i+1)
    plt.xticks([])
    plt.yticks([])
    plt.grid(False)
    plt.imshow(train_images[i], cmap=plt.cm.binary)
    plt.xlabel(train_labels[i])
plt.show()
```
