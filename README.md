# Bird Species Detection using Tensorflow Object Detection API

This is a deep learning project that I have done to detect bird species. The Faster R-CNN with ResNet 101 model has been used in this project to train datasets to categorise bird species based on images provided by my professor Dr. Carl Chalmers. Furthermore, a comparison with the SSD Mobilenet model will be made to assess how this model compares. 

## The Data
The images of bird species provided by my lecturer, Dr. Carl Chalmers, will serve as the input dataset for my project. In total, our professor provided us with approximately 4000 images of four different bird species, from which we were required to tag three unique bird classes with a minimum of 500 tags each class. 

*All Bird Species*:
- Erithacus_Rubecula
- Periparus_ater
- Pica_pica
- Turdus_merula

*Selected Bird Species*:
- Erithacus_Rubecula
- Periparus_ater
- Pica_pica

Because of the some differences within these species, I've chosen the three bird species mentioned above to implement my model. The colour of *Erithacus Rubecula* was distinct from the others, while *Pica pica* had a long tail that will aid in identification, and finally *Periparus ater* was similar to Pica pica but with different shades and a shorter tail. These differences will really help my model to train properly. For these reasons, I decided to choose these 3 bird species for my input.

For the model, a total of 2402 photos were tagged with RenomTag. There were 801 images tagged with *Erithacus Rubecula*, 801 images with *Periparus ater*, and 801 images with *Pica pica*. Also, the tags are in the pascal VOC format. The dataset has been divided into train/test split with the percentage of 90/10 respectively. 

## For training and evaluation of the model (Faster R-CNN)

I decided to chose **Faster R-CNN** with ResNet101 as the base network for extracting features rather than VGG because they use less kernels and enhance the performance of neural network with more layers. A 1024x1024 image size is being used as we are identifying birds, which take up only a little portion of the image. As a result, if I reduce the size of the image, it may lose many of its valuable qualities.

I started with 5000 steps and gradually increased it to 20000 before settling on 10000 steps because it was performing well and with great accuracy. Also, above 10000 steps the model performance was nearly identical, and below this, the model performed okay where the value of loss was not satisfying enough according to the tensorboard graphs.

The graphical representation of all train and eval data and also the prediction that has been done by the model is done using TensorBoard for which the screenshot can be seen below:

For Loss:

![F-RCNN](https://user-images.githubusercontent.com/29011734/163980697-af331941-f70d-4ef0-986d-e1f26681578a.png)

For Learning rate:

![F-RCNN_2](https://user-images.githubusercontent.com/29011734/163980759-9ec46238-66f7-49dc-83ab-94323bac1165.png)

For steps per sec:

![F-RCNN_3](https://user-images.githubusercontent.com/29011734/163980919-4539315f-7250-4f01-bff3-8b65d9a8da50.png)

Some output images of predicted birds:

![Predict_4](https://user-images.githubusercontent.com/29011734/163981160-e3a132a3-9d6d-40ff-891f-123617993708.png)

![Predict_2](https://user-images.githubusercontent.com/29011734/163980969-482fab1c-5f75-4f1f-93cc-d8a05636d03c.png)

![Predict_3](https://user-images.githubusercontent.com/29011734/163980981-97684cc4-60d0-4a9a-ab7f-9f5641b071f6.png)








