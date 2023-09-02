# Object_detection Yolo nas 
Here i used a pre trained state of the art model called Yolo_nas_s(small version) developed by super gradients.
It was pretrained on the  coco dataset.
I imported the model and trained it on my dataset which was taken from Kaggle -Plastic Bottles Dataset.
The dataset was loaded on google drive which i then mounted to the colab notebook so all the files generated will be save there which includes the best performing weights for my custom dataset.
Import dataloader provided by super gradients and through this the dataloader namely coco_detection_yolo_format_train, coco_detection_yolo_format_val our cutom data can be loaded with the ability to control batch size, num workers, class names and where to access and saved the data.

### applying custom transformations
train_data.dataset.transforms
### visualizing data after transformation
train_data.dataset.plot()
The number and name of classes here is only one which is 'bottle'
![sample of training data](https://user-images.githubusercontent.com/26987970/265216951-03b1fb57-f86b-424d-93cf-c38489369572.png)

After this i just needed to import the models and using models.get() method along with specifying some arguments like MODEL_ARCH, num_classes=len(dataset_params['classes']), pretrained_weights="coco".
For training import Trainer which contians all the trining functionality, i created its instance and called train method ......taining begins.
The hyperparameters are regulated by train params dict which feed into the trainer,train as a argument.
I trained my model for a mere 10 epochs on 1742 images of plastic bottles.
All that left was extraction of best weights and load it up and run predictions real life images.
Here are he results (for a 10 epoch trianing i got pretty good result and acceptable map).
![model predictions on real life images](https://user-images.githubusercontent.com/26987970/265217583-c9e0466f-5562-4e78-995d-14d076bcf398.png)

(url)



