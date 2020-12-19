Before checking the files in the document or conducting your experiments, please read this file carefully and understand the functions/usage of all the files.

Besides, we will explain the detailed process of this experimental design, including dataset, algorithms, improvement and comparisons, which are essentially important as well.



The "Ipynb_checkpoints" is a check node for the jupyter notebook, which can be ignored.  

"c_cnn" is a project for SCM(single chip microcomputer). This project can embed the final model into the SCM. We will explain the model in the following.

"cnn1" is the raw C file for the project above. If you don't have a STC8 SCM, you can use this C file to conduct a simulative experiment.

We mainly uses two datasets from Kaggle. The first one is concerned about mental health, and the other one is about heart-disease. We deliberately choose these two datasets, because they are both about health.  We saved the processed files so that readers can easily understand what we have done during the data pre-processing. "1.xlsx" is about the second dataset, "comparison.xlsx" is about the final comparison between the original algorithm and the improved algorithm, and all the other xls/xlsx files are about the first dataset. 

The "h5" files save the deep learning models, which can be reloaded by Keras frame.

"deal_txt.ipynb" shows how we deal with the txt files. "experiment1.ipynb" and "experiment2.ipynb" show how we conduct the experiments to compare different algorithms. "mental_health.ipynb" visualizes the first dataset, which helps the readers to understand the dataset better. Most of code in this file consulted the code from kaggle. 

Because we plan to embed our algorithm into SCM, the principle of which is well-matched with Random Forest, we try to use Random Forest from scratch(some well-optimized modules such as sk-learn are hard to be embedded). "myrf.ipynb" and "rt_tune.ipynb" show the process, but the accuracy of the simplified random forest is far from satisfactory. Therefore, we do not use it in the end.

"tune.ipynb" is an important file, which shows the process of utilizing, tuning and comparing different algorithms, including Random Forest, SVM, Logistic Regression and Deep Learning. We use various principles, including accuracy, recall, running time and the number of parameters. We find that, although DL(Deep Learning) needs more parameters, it is clearly faster and more accurate than other algorithms. Therefore, we finally decided to embedded DL into SCM. Traditionally, we use dnn to deal with one dimentional data. This time, we try to use one dimentional cnn for feature extraction and compare the two algorithms by two dataset we mentioned above, conducting 30 different independent experiments.

