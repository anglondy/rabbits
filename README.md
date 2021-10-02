# rabbits
Object detection with selective search and simple classifier

Dataset was taken from https://public.roboflow.com/object-detection/cottontail-rabbits-video-dataset
Original dataset contains only 87 images of rabbits with labels(bounding boxes). 
Link leads to already augmented dataset(1980 train, 19 validation, 10 test images).

For detecting bounding boxes I used Selective Search from OpenCV. 
To classify boxes as rabbit or not, I used transfer learning (VGG19, ImageNet), because small networks were stuck at 90% accuracy on validation set.
train_rabbit.ipynb contains all code i used to train the network (can't load it to Github, to big file).
test_rabbit.ipynb shows network performance on the test set as well as all time and accuracy tests.

My final words:
Selective Search is a fairly powerful low-level algorithm, but it cannot be used in real-time applications.
Recommended setting - default. 
If only recall matters, it might be good idea to resize the image to a lower resolution before searching boxes to save time.
I have not tried using a small network because it will not greatly reduce the timings.
