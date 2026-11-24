# CNNs from Scratch, Grad-CAM and PCA-Initialized Filters

Project 1 of CS 437 Deep Learning, LUMS, Spring 2026. Three notebooks that go from writing convolution by hand, to explaining a compact CNN's decisions, to initializing filters from PCA.

## Parts

| Part | Notebook | What it covers |
| --- | --- | --- |
| 1. CNN and bottleneck from scratch | [`1_cnn_from_scratch_and_bottleneck.ipynb`](notebooks/1_cnn_from_scratch_and_bottleneck.ipynb) ([nbviewer](https://nbviewer.org/github/SameerRahil/Deep-Learning-CNNs-GradCAM-PCA/blob/main/notebooks/1_cnn_from_scratch_and_bottleneck.ipynb)) | Conv2D and cross-entropy loss written by hand (forward and backward passes, checked against PyTorch), then a standard CNN and a bottleneck CNN trained with Adam on CIFAR-10 and compared on parameters and accuracy. |
| 2. Efficient CNN with Grad-CAM | [`2_efficient_cnn_gradcam.ipynb`](notebooks/2_efficient_cnn_gradcam.ipynb) ([nbviewer](https://nbviewer.org/github/SameerRahil/Deep-Learning-CNNs-GradCAM-PCA/blob/main/notebooks/2_efficient_cnn_gradcam.ipynb)) | A CNN under one million parameters for CIFAR-10, its training curves, and a Grad-CAM implementation with heatmap visualizations of what the network looks at. |
| 3. PCA meets CNNs | [`3_pca_meets_cnns.ipynb`](notebooks/3_pca_meets_cnns.ipynb) ([nbviewer](https://nbviewer.org/github/SameerRahil/Deep-Learning-CNNs-GradCAM-PCA/blob/main/notebooks/3_pca_meets_cnns.ipynb)) | Feature-extraction hooks, PCA of the CNN's latent spaces, convolutional filters initialized from PCA components, and an ablation over the PCA component budget on Fashion-MNIST. |

If GitHub cannot display a notebook, the nbviewer link next to it opens the same file.

## Results

| Model | Data | Parameters | Test accuracy |
| --- | --- | --- | --- |
| Standard CNN (from scratch layers) | CIFAR-10 | 620,810 | 78.04% |
| Bottleneck CNN | CIFAR-10 | 121,866 (about 5x fewer) | 72.86% final, 76.15% best |
| Efficient CNN | CIFAR-10 | 991,690 | 87.91% |
| CNN, random initialization | Fashion-MNIST | | 92.24% |
| CNN, PCA-initialized filters | Fashion-MNIST | | 91.42% (ahead after epoch 1: 88.53% vs 87.60%) |

In the component-budget ablation, accuracy rose from 83.26% with the smallest budget to 92.27% with all 784 components.

## Stack

Python, PyTorch, NumPy, scikit-learn, Matplotlib.

## Running the notebooks

The notebooks were run on Google Colab or Kaggle with a GPU. Open one in Colab, set the runtime to GPU, and run the cells in order. CIFAR-10 and Fashion-MNIST download through torchvision.

## About

Coursework for CS 437 Deep Learning, LUMS, Spring 2026, shared as part of my portfolio (course grade: A+). The notebooks keep the original handout text and my implementations, answers and outputs.

If you are taking this course, please do your own work.

**Sameer Rahil**, BS Computer Science, LUMS. More projects at [github.com/SameerRahil](https://github.com/SameerRahil).
