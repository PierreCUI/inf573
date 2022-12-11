In order to run this program properly, you need to follow these steps

1. Download the code for yolov5 from github at https://github.com/ultralytics/yolov5/tree/v5.0
2. Merge the file here with the yolov5 code, overwriting the yolov5 parts
3. We do not provide you with a training set (it is too large), but we do provide a trained model (runs/train) that you can use directly
4. if you need to do a new train, please follow the steps in the paper and make sure that all the paths are correct

Please follow the steps to do the new train-test

1. Use CutVideo to get the pictures if input is video
2. Use labelimg to label the pictures (with predefined_classes.txt)
3. Use Split to do the train_val_split
4. Use python train.py in cmd to start the training
--weights is the location of the model
--cfg is the location of the yaml in models
--data is the location of the yaml in data
--img-size is the size of the input image
--device is the gpu/cpu you are using
--epochs, --batch--size and --workers depend on your computer
5. Use tensorboard --logdir=runs/train in cmd and visit http://localhost:6006/ to see the result of training
6. Use python detect.py in cmd to do the test
--weights is the location of the trained model
--source is the location of the test data
--img-size is the size of image of the test input
--device is the gpu/cpu you are using

If you meet with RAM problem, please try to change the num_workers=nw in datasets line 81 to num_workers=0.
If you want the training data, please contact me asap.