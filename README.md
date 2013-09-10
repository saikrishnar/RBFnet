RBFnet
======

RBF Network using Theano, climin, and sklearn. 

Theano [http://deeplearning.net/software/theano/] and [https://github.com/Theano/Theano] is a python library which makes it easy to do symbolic computation with multidimensional arrays (see numpy.ndarray). 

Climin [https://climin.readthedocs.org/en/latest/] and [https://github.com/BRML/climin] is a python library for optimization. 

Sklearn [http://scikit-learn.org/stable/] and [https://github.com/scikit-learn/scikit-learn] is a python library with a large number of machine learning algorithms already implemented.

This project shows how the three can be used together for developing and training new machine learning algorithms. 

Theano
------

Theano is an incredible library from the perspective of a machine learning researcher. The basic usage pattern is:

1) Write symbolic code in python implementing your algorithm. Usually this is less than 20 lines because of the expressiveness of python and the ease with which multidimensional arrays are handled in Theano. 

2) Use Theano's automatic differentiation capabilities to calculate the gradients of the error with respect to model parameters. The gradient is hugely important for optimization, and not having to derive it by hand is a huge time saver and bug killer when it comes to developing new algorithms. 

3) Theano compiles your symbolic code to C code, optimizing as much as possible. This is another awesome feature, and I noticed huge speedups using it compared to naive python/numpy code.

4) Pass the compiled functions and gradients to your optimization libraries.


Climin
------



Images
======

![alt tag](https://raw.github.com/dhammack/RBFnet/master/circular_data.png)
![alt tag](https://raw.github.com/dhammack/RBFnet/master/8_gaussians.png)
![alt tag](https://raw.github.com/dhammack/RBFnet/master/hard_5_classes.png)
![alt tag](https://raw.github.com/dhammack/RBFnet/master/6_classes_sgd.png)
![alt tag](https://raw.github.com/dhammack/RBFnet/master/seperable_5_gaussians.png)
![alt tag](https://raw.github.com/dhammack/RBFnet/master/4_classes_easy.png)
![alt tag](https://raw.github.com/dhammack/RBFnet/master/6_classes_seperable.png)
Graphics by Matplotlib. 


Note
====

I made a change to gd.py in climin so that the optimizer can report cost per minibatch. It doesn't help with optimization at all, but it's something I like to see afterwards to kinow that things were working correctly. If you try to use 'sgd' as an optimizer, make sure to replace the gd.py in your climin installation with the version in this repo.

