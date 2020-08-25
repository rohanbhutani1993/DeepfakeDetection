# DeepfakeDetection
This repository gives a brief idea to classify a video as a deepfake or an original video. Follow the steps below to replicate the results.
1. The dataset for this problem was taken from 140k faces dataset from kaggle. To add more images for training the model, I used 2000 videos that were provided by google as part of their deepfake dataset. It consists of 1000 real videos randomly taken from youtube and their corresponding 1000 fake videos. I ran MTCNN on these 2000 videos to extract faces from them. This resulted in an extra 31,984 images. The code for this step can be found in my FacialRecognitionMTCNN repository.
2. The dataset was then divided into three separate folders - train, test and valid.
3. Data flows were created for each folder using ImageDataGenerator. A few data augmentation techniques were applied such as rotation, zooming, horizontal flip etc. The target size for each image was (224, 224).
4. The model used for classification was a pretrained Densenet model using imagenet weights because the training data was way too small to achieve a good result by building a custom CNN. Hence, transfer learning was used.
5. The model was trained for 5 epochs and achieved 94% accuracy on the test set and 95% on the validation set.
