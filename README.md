# IR-object-detection

### Training YOLOv5 on a Custom Dataset of Thermal Images

* Set up the code
    * clone yolov5 to machine
    * install dependencies (pip install -r yolov5/requirements.txt) (I think conda should work too)
    * import required models (if not already done)
* Importing dataset
    * make a new directory (mkdir)
    * download the dataset into it

Details about dataset:
We have found one dataset that may be adequate for our purposes, a portion of it is included in the folder 'FLIR_Dataset'. Since the training and validation frames from this set are taken from a vehicle, it is best suited for that application. However, it may be general enough for our purposes. The provided annotation of the dataset is in similar to Microsoft's COCO annotation file format, but with added modifications for FLIR's proprietary dataset management tool called Conservator. The annotations will have to be changed to fit the yolov5 model (where each image annotation is a .txt file where each line describes a bounding box, shown below). Converters can be found online, or they can be manually created.

![Alt text](https://blog.paperspace.com/content/images/size/w1000/2021/03/image-25.png "Bounding Boxes")

* Partition the dataset into train, validation and test sets containing approximately 80%, 10%, and 10%, respectively
    * the FLIR dataset is already split

* Specify training options: batch, epochs, data, workers, cfg(model architecture: yolo5s.yml, yolov5m.yml, yolov5l.yml, yolo5x.yml), weights (pretrained weights, if from scratch, use --weights ' ')
   * I will likely use yolo5s.yml since it is the smallest model

* Data config file, specify:
   * locations of training, testing, and validation images
   * number of classes in the dataset
   * names of the classes in the dataset

* Hyperparameter config file (unlikely that I will change anything)

* Customizing network architecture (unlikely that I will change anything)

* When training the model, choose:
   * batch size (# of training examples in one forward/backward pass)
   * image size (# pixels)
   * number of epochs (complete passes through training set)
 
Inference
* 
