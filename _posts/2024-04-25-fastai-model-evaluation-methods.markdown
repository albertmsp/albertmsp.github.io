---
layout: post
title:  "Fastai model evaluation"
date:   2024-04-25 14:30:30 +0800
categories: jekyll update
---
There are many ways for us to evaluate the deep learning model, for the fastai models, there are two ways: confusion matrix and t_SNE

For confusion matrix:

Confusion matrix is a tool often used in classification to visualize the performance of an algorithm. Each row of the matrix represents the instances in an actual class, while each column represents the instances in a predicted class. This allows you to see where the model might be confusing two classes and is useful for identifying misclassifications.
![Image of confusion matrix](/images/confusion_matrix.png)

For t_SNE:

'''console
# Get the activations from the model
def get_activations(learner, dataloader):
    learner.model.eval()
    activations = []
    labels = []
    with torch.no_grad():
        for xb, yb in dataloader:
            out = learner.model(xb)
            activations.append(out)
            labels.append(yb)
    activations = torch.cat(activations).cpu().numpy()
    labels = torch.cat(labels).cpu().numpy()
    return activations, labels

# Get activations and labels
activations, labels = get_activations(learn, dls.valid)

# Perform t-SNE to reduce dimensionality
tsne = TSNE(n_components=2, random_state=42)
activations_tsne = tsne.fit_transform(activations)

# Plot t-SNE
plt.figure(figsize=(10, 8))
for i, class_name in enumerate(dls.vocab):
    idx = labels == i
    plt.scatter(activations_tsne[idx, 0], activations_tsne[idx, 1], label=class_name, alpha=0.7)
plt.title('t-SNE Plot of CIFAR-10 Classes')
plt.legend()
plt.show()
'''

t-SNE (t-distributed Stochastic Neighbor Embedding) is a machine learning algorithm for visualization developed by Laurens van der Maaten and Geoffrey Hinton. It reduces high-dimensional data to two or three dimensions so that it can be plotted on a graph. This technique is particularly good at creating a map that reveals structures at many different scales, which is crucial for understanding complex datasets with many variables.
![Image of confusion matrix](/images/t_SNE.png)
