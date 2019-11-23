1)Logs of 20 Epoc.

```
Train on 60000 samples, validate on 10000 samples
Epoch 1/20

Epoch 00001: LearningRateScheduler setting learning rate to 0.003.
60000/60000 [==============================] - 9s 142us/step - loss: 0.5439 - acc: 0.8464 - val_loss: 0.1710 - val_acc: 0.9641
Epoch 2/20

Epoch 00002: LearningRateScheduler setting learning rate to 0.0022744503.
60000/60000 [==============================] - 6s 96us/step - loss: 0.2650 - acc: 0.9188 - val_loss: 0.0572 - val_acc: 0.9875
Epoch 3/20

Epoch 00003: LearningRateScheduler setting learning rate to 0.0018315018.
60000/60000 [==============================] - 6s 95us/step - loss: 0.2050 - acc: 0.9364 - val_loss: 0.0511 - val_acc: 0.9897
Epoch 4/20

Epoch 00004: LearningRateScheduler setting learning rate to 0.0015329586.
60000/60000 [==============================] - 6s 96us/step - loss: 0.1775 - acc: 0.9432 - val_loss: 0.0457 - val_acc: 0.9877
Epoch 5/20

Epoch 00005: LearningRateScheduler setting learning rate to 0.0013181019.
60000/60000 [==============================] - 6s 94us/step - loss: 0.1583 - acc: 0.9475 - val_loss: 0.0366 - val_acc: 0.9918
Epoch 6/20

Epoch 00006: LearningRateScheduler setting learning rate to 0.0011560694.
60000/60000 [==============================] - 6s 98us/step - loss: 0.1448 - acc: 0.9501 - val_loss: 0.0305 - val_acc: 0.9927
Epoch 7/20

Epoch 00007: LearningRateScheduler setting learning rate to 0.0010295127.
60000/60000 [==============================] - 6s 96us/step - loss: 0.1347 - acc: 0.9517 - val_loss: 0.0280 - val_acc: 0.9930
Epoch 8/20

Epoch 00008: LearningRateScheduler setting learning rate to 0.0009279307.
60000/60000 [==============================] - 6s 95us/step - loss: 0.1281 - acc: 0.9530 - val_loss: 0.0255 - val_acc: 0.9928
Epoch 9/20

Epoch 00009: LearningRateScheduler setting learning rate to 0.0008445946.
60000/60000 [==============================] - 6s 96us/step - loss: 0.1214 - acc: 0.9534 - val_loss: 0.0237 - val_acc: 0.9937
Epoch 10/20

Epoch 00010: LearningRateScheduler setting learning rate to 0.0007749935.
60000/60000 [==============================] - 6s 96us/step - loss: 0.1177 - acc: 0.9539 - val_loss: 0.0252 - val_acc: 0.9927
Epoch 11/20

Epoch 00011: LearningRateScheduler setting learning rate to 0.0007159905.
60000/60000 [==============================] - 6s 98us/step - loss: 0.1134 - acc: 0.9547 - val_loss: 0.0205 - val_acc: 0.9945
Epoch 12/20

Epoch 00012: LearningRateScheduler setting learning rate to 0.000665336.
60000/60000 [==============================] - 6s 96us/step - loss: 0.1108 - acc: 0.9545 - val_loss: 0.0207 - val_acc: 0.9948
Epoch 13/20

Epoch 00013: LearningRateScheduler setting learning rate to 0.0006213753.
60000/60000 [==============================] - 6s 96us/step - loss: 0.1088 - acc: 0.9546 - val_loss: 0.0214 - val_acc: 0.9940
Epoch 14/20

Epoch 00014: LearningRateScheduler setting learning rate to 0.0005828638.
60000/60000 [==============================] - 6s 97us/step - loss: 0.1061 - acc: 0.9548 - val_loss: 0.0191 - val_acc: 0.9943
Epoch 15/20

Epoch 00015: LearningRateScheduler setting learning rate to 0.0005488474.
60000/60000 [==============================] - 6s 97us/step - loss: 0.1014 - acc: 0.9565 - val_loss: 0.0215 - val_acc: 0.9933
Epoch 16/20

Epoch 00016: LearningRateScheduler setting learning rate to 0.0005185825.
60000/60000 [==============================] - 6s 95us/step - loss: 0.1007 - acc: 0.9562 - val_loss: 0.0204 - val_acc: 0.9944
Epoch 17/20

Epoch 00017: LearningRateScheduler setting learning rate to 0.000491481.
60000/60000 [==============================] - 6s 96us/step - loss: 0.0987 - acc: 0.9568 - val_loss: 0.0186 - val_acc: 0.9946
Epoch 18/20

Epoch 00018: LearningRateScheduler setting learning rate to 0.0004670715.
60000/60000 [==============================] - 6s 97us/step - loss: 0.0992 - acc: 0.9571 - val_loss: 0.0192 - val_acc: 0.9945
Epoch 19/20

Epoch 00019: LearningRateScheduler setting learning rate to 0.0004449718.
60000/60000 [==============================] - 6s 95us/step - loss: 0.0990 - acc: 0.9564 - val_loss: 0.0233 - val_acc: 0.9932
Epoch 20/20

Epoch 00020: LearningRateScheduler setting learning rate to 0.000424869.
60000/60000 [==============================] - 6s 98us/step - loss: 0.0984 - acc: 0.9556 - val_loss: 0.0200 - val_acc: 0.9944
<keras.callbacks.History at 0x7feab08c9320>

````

Highest accuracy is 99.48% with 12,796 parameters.

2) Model.evaluate Results ***[0.019959482657676563, 0.9944]***

3)***Strategy***
- I have started from a very small kernal size(8) inorder to reduce parameters, in most of the network you have designed the channels 
  are bigger in the starting, the layers which follow this layer intern increases the number of parameters exponentially.
  
- Then i have increase the next layer with a 16 channels in a hope that it will capture most of the edges and gradients in the images.
  after that i have added maxpooling and reduced the channel size to 10.
 
- THEN increased channel size to 16 where it will start to capture parts of the object and the next layer is also a 16 where further parts
  of the object will be captured.
