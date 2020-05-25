# bird_classifier
CNN used to classify 175 species of birds based on a single image.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cjelgin/bird_classifier/blob/master/Bird_Classifier.ipynb)

This project is essentially using transfer learning to classify images of birds by respective species from 175 choices. The dataset if publicly available from Kaggle [here](https://www.kaggle.com/gpiosenka/100-bird-species). The model is a CNN built from pre-trained layers from the Xception image classification model. After training for a total of 10 epochs, the model achieves approximately 98% validation accuracy.


The model is packaged into a Docker image available at ???, which uses the TensorFlow Serving protocol. The Python notebook, "TFServing_Bird_Classifier_API_Test.ipynb" contains commands for loading a candidate test image, "STORK_BILLED_KINGFISHER.npy", and making a prediction from the model using TensorFlow Serving.

The Python notebook "Bird_Classifier.ipynb" containes the commands used to preprocesss the data and train the model. The file "build_tf_serving_container.txt" contains the shell commands used to package the model into a TensorFlow Serving container. The command used to run the container is:

$ docker run -it -p 8500:8500 -p 8501:8501 --name bird_classifier bird_classifier
