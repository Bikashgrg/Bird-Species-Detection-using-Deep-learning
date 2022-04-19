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

## For inferencing model with external images of bird species

Below are some of the outputs generated using Faster R-CNN when external data is being used:

![Screenshot (377)](https://user-images.githubusercontent.com/29011734/163982416-5301b05f-09dc-4030-9be5-07c81021eedb.png)

![Screenshot (378)](https://user-images.githubusercontent.com/29011734/163982433-a56d76c6-4087-458c-8d56-6c11192cdb21.png)

### Note:
All of the above information, along with screenshots of the output, can be found in the corresponding jupyter notebooks above, within their respective folders. 

## Conclusion

Finally, I'd like to highlight that the *Faster R-CNN* model outperformed the *SSD MobileNet* model in every parameter. Initially, I used the same config file parameter values for both models with 5000 training steps where *MobileNet* performed not good because it was having hard time recognised the birds. And even if it recongnises then either accuracy was low or wrongly classified the bird species in the images. This ensures that even with fewer steps, *Faster R-CNN* was able to function quite good. Finally, in terms of accuracy:

**SSD MobileNet** -> With 20 thousand steps it gave the accuracy of around 72%.

**Faster R-CNN** -> With 10 thousand steps it gave the accuracy of around 90%.

After confirming this, I attempted to make both models as good as possible by modifying the config file values. You can see all the perimeter modifications information for both *Faster R-CNN* and *SSD MobileNet* models in their respective *Inference* jupyter file.

