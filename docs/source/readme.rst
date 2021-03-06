==============================
MILK: MACHINE LEARNING TOOLKIT
==============================
Machine Learning in Python
--------------------------

Milk is a machine learning toolkit in Python.

Its focus is on supervised classification with several classifiers available:
SVMs (based on libsvm), k-NN, random forests, decision trees. It also performs
feature selection. These classifiers can be combined in many ways to form
different classification systems.

For unsupervised learning, milk supports k-means clustering and affinity
propagation.

Milk is flexible about its inputs. It optimised for numpy arrays, but can often
handle anything (for example, for SVMs, you can use any dataype and any kernel
and it does the right thing).

There is a strong emphasis on speed and low memory usage. Therefore, most of
the performance sensitive code is in C++. This is behind Python-based
interfaces for convenience.

New in 0.4.1
------------
- Fix important bug in multi-process gridsearch

New in 0.4.0
------------
- Use multiprocessing to take advantage of multi core machines (off by
  default).
- Add perceptron learner
- Set random seed in random forest learner
- Add warning to milk/__init__.py if import fails
- Add return value to ``gridminimise``
- Set random seed in ``precluster_learner``
- Implemented Error-Correcting Output Codes for reduction of multi-class
  to binary (including probability estimation)
- Add ``multi_strategy`` argument to ``defaultlearner()``
- Make the dot kernel in svm much, much, faster
- Make sigmoidal fitting for SVM probability estimates faster
- Fix bug in randomforest (patch by Wei on milk-users mailing list)

New in 0.3.10
-------------
- Add ext.jugparallel for integration with `jug <http://luispedro.org/software/jug>`_
- parallel nfold crossvalidation using jug
- parallel multiple kmeans runs using jug
- cluster_agreement for non-ndarrays
- Add histogram & normali(z|s)e options to ``milk.kmeans.assign_centroid``
- Fix bug in sda when features were constant for a class
- Add select_best_kmeans
- Added defaultlearner as a better name than defaultclassifier
- Add ``measures.curves.precision_recall``
- Add ``unsupervised.parzen.parzen``

New in 0.3.9
------------
- Add ``folds`` argument to ``nfoldcrossvalidation``
- Add ``assign_centroid`` function in milk.unsupervised.nfoldcrossvalidation
- Improve speed of k-nearest neighbour (10x on scikits-learn benchmark)
- Improve kmeans on newer numpy (works for larger datasets too)
- Faster kmeans by coding centroid recalculation in C++
- Fix gridminize for low count labels
- Fix bug with non-integer labels for tree learning

New in 0.3.8
------------
- Fix compilation on Windows

New in 0.3.7
------------
- Logistic regression
- Source demos included (in source and documentation)
- Add cluster agreement metrics
- Fix nfoldcrossvalidation bug when using origins


Features
--------
- Random forests
- Self organising maps
- SVMs. Using the libsvm solver with a pythonesque wrapper around it.
- Stepwise Discriminant Analysis for feature selection.
- Non-negative matrix factorisation
- K-means using as little memory as possible.
- Affinity propagation

License: MIT
Author: Luis Pedro Coelho (with code from LibSVM and scikits.learn)
Website: `http://luispedro.org/software/milk
<http://luispedro.org/software/milk>`__
API Documentation: `http://packages.python.org/milk/ <http://packages.python.org/milk/>`_
