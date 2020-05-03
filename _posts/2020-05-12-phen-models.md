---
title: 'Phenomenological Models and Machine Learning '
date: 2020-05-11
permalink: /posts/2020/05/phen-models/
tags:
  - complex systems
  - phenomenological modelling
---


Model creating process traditionally used to study the properties and to make predictions of behavior (dynamics) of various systems, 
both natural and artificial. Model is built on the basis of a certain set of measurements of system individual characteristics. 

 <!--more-->
Model is built on the basis of a certain set of measurements of system individual characteristics. Based on any theoretical approaches 
applicable to this system, one can try to obtain a formal description of the structure and (or) dynamics of this system, for example, as a set of mathematical equations describing the relationships between the parameters of the system under study. Such a model may be used for description of rather complex systems and phenomena (for example, temperature distribution over the surface of an object; exchange and transformation reactions of substances in a living cell; mechanical deformations when processing a part, etc.).
The classical approach of model creation (often called “mechanistic”) consists in forming a system of equations (differential, discrete-difference) that relate the system parameters; and for modeling dynamics, they also describe the dependence of these parameters on time. The basis of such a system of equations are known laws that can be applied to the description of the system (for example, the laws of thermodynamics, hydrodynamics, electrodynamics, chemical-kinetic reactions, mechanics, etc.).
If the laws of change and the relationship of parameters are unknown, they can be derived from a set of empirical data. During a series of measurements of system parameters under various conditions, one can obtain a set of tabular data and then find a functional dependence that most closely approximates the relationship between the parameter values.
This type of model has a certain drawback: the possibility of random changes in parameters and random effects on the system is not 
taken into account. The randomness factor may emerge be due to the following reasons:
+ random external influences and noises;
+ measurement errors, noise in measuring systems;
+ the random nature of changes in system parameters, for example, in the initial positions of the interacting elements of the system.

The randomness factor may be involved in system model by using probability distributions for parameters with random nature influences. Depending on the importance of the system parameters, randomly varying values can either be filtered out or evaluated further in the framework of a certain probabilistic model.
The generated mechanistic model of the system can be implemented in the form of numerical calculation algorithms for further computer calculations.
The described approach to creating a system model can be called "classic." The created model can be assessed for accuracy of matching with a real system by comparing model and actual data; also it may be determined within which parameters boundaries this model is most reliable.

The weakness of this modelling approach is increasingly noticeable in recent years. 

Total automation of system characteristics measurements in various fields (industry, finance, life sciences, social phenomena, media, nature studies, etc.), large amounts of digital measurements data creation, and the desire to obtain new qualitative conclusions on the basis of the available data arrays, it requires the creation of ever new models. The above “mechanistic” approach requires a large amount of analytical work for each individual task of model creation, which must be carried out by a whole group of researchers.

It is obvious that sooner or later the available resources (researchers with relevant education and specialization in the applied field; centers and laboratories; research funding opportunities, etc.)  will be exhausted, since the number of modelling tasks requiring study will be many orders of magnitude higher than these resources.

A more effective approach may be called the phenomenological modelling. Simplifying somewhat, it is possible to present its essence as the possibility of application of  some “universal modeling device” that implements the following principles:
+ “Device” does not realize the real physical (chemical, biological, ...) dependencies that describe the properties and dynamics of the system;
+ Its main property is the ability to infer a set of output values of state or system dynamics parameters,  which is as close as possible to values obtained empirically, having received some input parameters.

The computer implementation of the phenomenological model uses input and output data in the form of tabular (matrix) digital sets of values. A popular area of machine learning can also be considered a phenomenological modeling tool, perhaps the most effective today. The vast majority of machine learning models used today in research and software applications developing are neural networks of various architectures. Neural networks show strong possibilities in modeling very complex systems, such as images and video, audio, complex geometric shapes, relationships in natural language texts, etc.
It makes no sense to once again describe the classification and applied value of the developed machine learning algorithms, their advantages and disadvantages - all this stuff can be found in a huge variety of popular and scientific articles, lectures and courses. The most interesting are the following aspects of machine learning based phenomenological models of complex systems:

**1. Reproduction of the structural features of the simulated system**

Obviously, a trained ML-system in some form captures the relationship between the initial parameters, forming an “image” of the 
structure of the simulated system. The quality of the obtained “image of the structure” can be estimated by the following parameters:
+ The accuracy of the reproduction of the model output values  (compared with the "reference" values obtained empirically).
+ The limits of applicability of the model. With some inputs, the model can give much higher accuracy than with others. In particular, an unsuccessful learning strategy that leads to “overfitting” greatly worsens the quality of the model.

**2. Generative properties**

If a trained system model is provided with new input data that did not exist in the training set, new output data of the system can be obtained (for example, a new type of system state or a new system dynamics). These data will not be empirical, but modeled. If the input data initially have physical meaning (that is, they could be real), this makes it possible to obtain new, original states of this system, and possibly to obtain some of its new properties.
As an example of a computer implementation, we can cite the GANs that are now very popular, capable of generating, in particular, quite realistic implementations of various images, as well as, for example, people's voices, modifications to the form and shape of three-dimensional objects, etc.
To use the generative properties of ML-systems, you need to know the answers to the following questions:
+ *How to evaluate the realism of the newly generated data and understand that they really reflect the state of the structure of the real system?*
+ *What input parameters make the simulation realistic?*

**3. Improving the quality of simulated dependencies by noise reduction**

If the ML model really contains the structure of the simulated system, then we have the opportunity to separate the “superimposed” 
structural elements and / or system dynamics trajectories that are not inherent to this system. In particular, this may 
be a “measuring” noise that appears when metering the values of empirical parameters. It can be assumed that, after those 
“superimposed” data are deleted,  the output of the ML model will not contain noise, and their quality will be higher, which is 
important for the analysis of the system under study.

**4. Hierarchy of structure**

As a rule, any system considered “complex” has the property of “hierarchy”, that is, consists of several subsystems subordinate to each other. A good example is, for example, a protein molecule having several levels of structure. The lower levels in a sense “delegate” a number of properties to the following levels, determining their formation. As a result, the resulting structure of the protein molecule receives a certain set of properties that determine the possibility of interaction with other biochemical elements.
The hierarchical property, at the same time, can be observed in the architecture of multilayer neural networks (Deep neural networks), or Deep Learning systems. Such systems show high efficiency, for example, in the analysis of images during solving recognition problems. You can see how in such a network each layer (or a set of layers) solves the problem of image analysis at each hierarchy level, in approximate accordance with the hierarchy of the elements composing the image, and taking into account the interconnections between the levels.
The conclusion is that taking into account the hierarchy of the simulated system is important. 
+*Is it possible that evaluating the quality of a system model at each individual level of its hierarchy will significantly improve the quality of the model as a whole?*

**5. Determinism, noise and chaos**

In the case when we do not know system parameters functional interconnection, we can describe the current state of system parameters 
and their changes by probability distributions. In particular, when building a prediction of the dynamics of the system, 
the predicted value is determined as the most probable estimation, in accordance with the law of the probability distribution. 
At the same time, if the dynamics of the system is deterministic, and the functional law describing it is known, 
the forecast of the dynamics of the system will be more reliable. It can be assumed that these functional dependencies can be 
obtained by Machine Learning. In this case, it is advisable to know the answers to the following questions:
- *How to determine which of the system components are interconnected or are changed according to the functional law, and in which case they present purely random, noise behavior?

In case we try to simulate random noise, the model will fail. At the same time, one can give an example of the so-called “chaotic” processes known in the study of nonlinear dynamics. The chaotic process is complex oscillations, very similar to pure noise process, but they are generated by a deterministic system. Chaotic oscillations are unstable: with small changes in the initial values, closely located dynamic trajectories quickly diverge, and therefore the prediction of the dynamics of the system becomes impossible.
How can one determine what type of process takes place in the case under study:  noisy, chaotic, or complex mixture of several stable dynamic trajectories? Is there exist in nature other kinds of processes that are none of above?

**6. System analysis and control parameters determination**

A phenomenological model built on machine learning algorithms is not supposed to be built on the basis of real natural laws linking its main parameters. Nevertheless, if, as we believe, our model was able to form an “image of the structure” of the system under study, there is a potential opportunity to establish the relationship of this structure with real physical dependencies forming  the system.  In other words, we can try to connect the real physical parameters that determine the "nature" of the system with a set of parameters that are the "settings" of the phenomenological model. Thus, we will be able to analyze the behavior of the system under various conditions and the ability to control its behavior.

### Summary

Summary of those aspects leads to following conclusion.
The quality of the model can be significantly higher if, in addition to the dataset of the measured parameters of the model, 
the general system characteristics of the data source (the simulated system) are also used. Otherwise, we will have to use the 
largest “state space” of the ML-system, that is, we will need much more data, computational resources, training time, and the 
learning process will be more complicated. Predefined parameters of the data source structure will help to justify the architecture 
of the ML-system of the model and make it more relevant and plausible in relation to the simulated system.
