So far, I assume you have configured the targetd Linux-TensorFlow environment.

# How to train a model on your own dataset?
1. copy the Folder "Train_mode" to any directory on your PC or server;
2. put your training dataset into the Folder "input/train": "raw" is for the halftone image and "target" is for the ground-truth grayscale. (the paired halftone-grayscale must have the same filename, see the included examples);
3. put your validation datset into the Folder "input/val": "raw" is for the halftone image and "target" is for the ground-truth grayscale. (the paired halftone-grayscale must have the same filename, see the included examples);
4. run it by typing "python3 main.py" in your terminal interface.

Other remarks:
1) All the image size should be 256x256. If you really want to change it, please update IMG_WIDTH/IMG_HEIGH in the file named "model" at line7-8.;
2) If the training starts, the online generated inversed results of the halftone images of Folder "input/val/raw" will be saved in Folder "output";
3) If the training completes, the well-trained model will be saved in the Folder "model";


# How to test a well-trained model on inverse halftoning?
1. copy the Folder "Test_mode" to any directory on your PC or server;
2. put your testing dataset into the Folder "input": "raw" is for the halftone image and "target" is for the ground-truth grayscale. (the paired halftone-grayscale must have the same filename, see the included examples);
3. put the pre-trained model into Folder "model" (I have done this for you and you can also replace it with your newly trained model)
4. run it by typing "python3 main.py" in your terminal interface.

Other remarks:
1) All the image size should be 256x256. If you really want to change it, please update IMG_WIDTH/IMG_HEIGH in the file named "model" at line7-8.;
2) There is no need to use the real ground-truth grayscale in the folder "input/target", because they will not be used during testing.
But anyway you should put some images with the corresponding filename and resolution in, which is required by the data loader.