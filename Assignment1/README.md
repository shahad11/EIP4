1st DNN result  **[0.025798536649974994, 0.9911]**

Define the following.

**1- Convolution:-**
                Convolutions are dot multiplications between two similar or diffrent sized matrices. when convolving on top of a image
                each kernal extract diffrent kind of features.
                
**2-Filter/Kernal:- **
                Filter or kernal is a matrix which is used to convolv on top of another matrix(image in our case) to extract unique set 
                of features from the image. 
                
**3-Epocs:-**
           Epocs are going through all the calculations invoved in a convolution or neural network for all the images in the training set or
           test set.
           
**4-3x3 Convolution:-**
                    This type of convolution is a 3x3 matrix, dot multiplying on top of a matrix(image) to extract features form the image
                    3x3 convolution reduces the image size by 2x2(if not paded), and can incraese the channels by introducing more number
                    3x3 kernals. not used for reducing number of channels.
                    
**5-1x1 Convolution:-**
                   Dot multiplying on top of a image with 1x1 size ie with one number. this type of convolution, in most of the cases are
                   used to reduce the number of channels, which will reduce the computation.
                   
**6-Feature Map:-**
                Feature map's are the products of convolurion, which are basically extracted features after convolution.
                
**7-Activation function:-**
                        It is basicaly a fuction which determines what is the output from each pixcel(node). noramlly we will use RELU.
                        
**8-Receptive field:-**
                    Receptive field is how many pixcel(area) is seen by a pixcel after convolution, ie when a 3x3 matrix convolve on
                    top of a 5x5 matrix we get a 3x3 matrix, the bottom left of the resultant 3x3 matrix have seen only the 3x3 area
                    of bottom left in the 5x5 matrix(Local receptive field), it wont have any idea what will be on top right of the 5x5 matrix. when the
                    resultant 3x3 matrix is convolved by a 3x3 kernal resulting in a feature map of 1x1 which have seen all the image.

           
