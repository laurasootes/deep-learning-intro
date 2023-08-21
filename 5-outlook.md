---
title: "Outlook"
teaching: 10
exercises: 15
---

::: questions
- "How does what I learned in this course translate to real-world problems?"
- "What are next steps to take after this course?"
:::

::: objectives
- "Understand that what we learned in this course can be applied to real-world problems"
- "Identify next steps to take after this course"
:::

You have come to the end of this course.
In this episode we will look back at what we have learned so far, how to apply that to real-world problems, and identify
next steps to take to start applying deep learning in your own projects.

## Real-world application
To introduce the core concepts of deep learning we have used quite simple machine learning problems.
But how does what we learned so far apply to real-world applications?

To illustrate that what we learned is actually the basis of succesful applications in research,
we will have a look at an example from the field of cheminformatics.

We will have a look at [this notebook](https://github.com/matchms/ms2deepscore/blob/0.4.0/notebooks/MS2DeepScore_tutorial.ipynb).
It is part of the codebase for [this paper](https://doi.org/10.1186/s13321-021-00558-4).

In short, the deep learning problem is that of finding out how similar two molecules are in terms of their molecular properties,
based on their mass spectrum.
You can compare this to comparing two pictures of animals, and predicting how similar they are.
A siamese neural network is used to solve the problem.
In a siamese neural network you have two input vectors, let's say two images of animals or two mass spectra.
They pass through a base network. Instead of outputting a class or number with one or a few output neurons, the output layer
of the base network is a whole vector of for example 100 neurons. After passing through the base network, you end up with two of these
vectors representing the two inputs. The goal of the base network is to output a meaningful representation of the input (this is called an embedding).
The next step is to compute the cosine similarity between these two output vectors,
cosine similarity is a measure for how similar two vectors are to each other, ranging from 0 (completely different) to 1 (identical).
This cosine similarity is compared to the actual similarity between the two inputs and this error is used to update the weights in the network.

Don't worry if you do not fully understand the deep learning problem and the approach that is taken here.
We just want you to appreciate that you already learned enough to be able to do this yourself in your own domain.

::: instructor
You don't have to use this project as an example.
It works best to use a suitable deep learning project that you know well and are passionate about.
:::
::: challenge
## Exercise: A real-world deep learning application

1. Looking at the 'Model training' section of the notebook, what do you recognize from what you learned in this course?
2. Can you identify the different steps of the deep learning workflow in this notebook?
3. (Optional): Try to fully understand the neural network architecture from the first figure of [the paper](https://doi.org/10.1186/s13321-021-00558-4)

:::: solution
## Solution
1. The model summary for the Siamese model is more complex than what we have seen so far,
but it is basically a repetition of Dense, BatchNorm, and Dropout layers.
The syntax for training and evaluating the model is the same as what we learned in this course.
EarlyStopping as well as the Adam optimizer is used.
2. The different steps are not as clearly defined as in this course, but you should be able to identify '3: Data preparation',
'4: Choose a pretrained model or start building architecture from scratch', '5: Choose a loss function and optimizer', '6: Train the model',
'7: Make predictions' (which is called 'Model inference' in this notebook), and '10: Save model'.
::::
:::

Hopefully you can appreciate that what you learned in this course, can be applied to real-world problems as well.

::: callout
## Extensive data preparation
You might have noticed that the data preparation for this example is much more extensive than what we have done so far
in this course. This is quite common for applied deep learning projects. It is said that 90% of the time in a
deep learning problem is spent on data preparation, and only 10% on modeling!
:::

## Next steps
You now understand the basic principles of deep learning and are able to implement your own deep learning pipelines in Python.
But there is still so much to learn and do!

Here are some suggestions for next steps you can take in your endeavor to become a deep learning expert:

* Learn more by going through a few of [the learning resources we have compiled for you](learners/reference.md#external-references)
* Apply what you have learned to your own projects. Use the deep learning workflow to structure your work.
Start as simple as possible, and incrementally increase the complexity of your approach.
* Compete in a [Kaggle competition](https://www.kaggle.com/competitions) to practice what you have learned.
* Get access to a GPU. Your deep learning experiments will progress much quicker if you have to wait for your network to train
in a few seconds instead of hours (which is the order of magnitude of speedup you can expect from training on a GPU instead of CPU).
Tensorflow/Keras will automatically detect and use a GPU if it is available on your system without any code changes.
A simple and quick way to get access to a GPU is to use [Google Colab](https://colab.google/)

::: keypoints
- "Although the data preparation and model architectures are somewhat more complex,
what we have learned in this course can directly be applied to real-world problems"
- "Use what you have learned in this course as a basis for your own learning trajectory in the world of deep learning"
:::
