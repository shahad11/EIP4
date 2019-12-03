
Final validation acuuracy for base network :- ``` 82.92 ```

Model definition

```
#new model
                                                                        # img siz    RF
model1 = Sequential()
model1.add(SeparableConv2D(16,3, padding='same',input_shape=(32, 32, 3)))# 32x32     3x3
model1.add(Activation('relu'))
model1.add(BatchNormalization())
model1.add(Dropout(0.2))

model1.add(SeparableConv2D(32,3, padding='same'))                        #32x32     5x5
model1.add(Activation('relu'))
model1.add(BatchNormalization())
model1.add(Dropout(0.2))

model1.add(SeparableConv2D(64,3, padding='same'))                        #32x32      7x7
model1.add(Activation('relu'))
model1.add(BatchNormalization())
model1.add(Dropout(0.2))

model1.add(SeparableConv2D(128,3, padding='same'))                      #32x32      9x9
model1.add(Activation('relu'))
model1.add(BatchNormalization())
model1.add(Dropout(0.2))

#model1.add(SeparableConv2D(256,3, padding='same'))                     #32x32       11x11
#model1.add(Activation('relu'))
#model1.add(BatchNormalization())
#model.add(Dropout(0.1))

#adding max pool

model1.add(MaxPooling2D(pool_size=(2,2)))                             #16x16        22x22

#reducing channel size by 1x1 kernal

model1.add(Convolution2D(16,1))                                       #16x16        22x22
model1.add(Activation('relu'))


model1.add(SeparableConv2D(32,3, padding='same'))                     #16x16          24x24 
model1.add(Activation('relu'))
model1.add(BatchNormalization())
model1.add(Dropout(0.2))

model1.add(SeparableConv2D(64,3, padding='same'))                     #16x16          26x26 
model1.add(Activation('relu'))
model1.add(BatchNormalization())
model1.add(Dropout(0.2))

model1.add(SeparableConv2D(64,3, padding='same'))                     #16x16          28x28 
model1.add(Activation('relu'))
model1.add(BatchNormalization())
model1.add(Dropout(0.2))

model1.add(SeparableConv2D(128,3, padding='same'))                     #16x16          30x30 
model1.add(Activation('relu'))
model1.add(BatchNormalization())
model1.add(Dropout(0.2))

model1.add(SeparableConv2D(256,3, padding='same'))                     #16x16          32x32
model1.add(Activation('relu'))
model1.add(BatchNormalization())
model1.add(Dropout(0.2))

model1.add(MaxPooling2D(pool_size=(2,2)))                              #8x8            64x64

model1.add(Convolution2D(16,1))
model1.add(Activation('relu'))

model1.add(SeparableConv2D(32,3))                                      # 6x6           66x66 
model1.add(Activation('relu'))
model1.add(BatchNormalization())
model1.add(Dropout(0.2))

model1.add(Convolution2D(10,6))                                         #1x1           71x71  
model1.add(BatchNormalization())
model1.add(Dropout(0.2))
#model1.add(Activation('relu'))

model1.add(Flatten())
model1.add(Activation('softmax'))

model1.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])


model1.summary()


```

Logs for 50 epocs:-

```
Epoch 1/50
390/390 [==============================] - 57s 147ms/step - loss: 1.7884 - acc: 0.3591 - val_loss: 1.9573 - val_acc: 0.3040
Epoch 2/50
390/390 [==============================] - 49s 127ms/step - loss: 1.5291 - acc: 0.4621 - val_loss: 2.0348 - val_acc: 0.2893
Epoch 3/50
390/390 [==============================] - 49s 126ms/step - loss: 1.3865 - acc: 0.5180 - val_loss: 1.5452 - val_acc: 0.4620
Epoch 4/50
390/390 [==============================] - 49s 126ms/step - loss: 1.2559 - acc: 0.5664 - val_loss: 1.5454 - val_acc: 0.4672
Epoch 5/50
390/390 [==============================] - 49s 127ms/step - loss: 1.1613 - acc: 0.5988 - val_loss: 1.3915 - val_acc: 0.5113
Epoch 6/50
390/390 [==============================] - 49s 126ms/step - loss: 1.0915 - acc: 0.6241 - val_loss: 1.1818 - val_acc: 0.5967
Epoch 7/50
390/390 [==============================] - 49s 126ms/step - loss: 1.0301 - acc: 0.6429 - val_loss: 1.0662 - val_acc: 0.6386
Epoch 8/50
390/390 [==============================] - 49s 126ms/step - loss: 0.9868 - acc: 0.6572 - val_loss: 1.0825 - val_acc: 0.6254
Epoch 9/50
390/390 [==============================] - 49s 126ms/step - loss: 0.9465 - acc: 0.6694 - val_loss: 0.9274 - val_acc: 0.6899
Epoch 10/50
390/390 [==============================] - 50s 127ms/step - loss: 0.9054 - acc: 0.6842 - val_loss: 0.9816 - val_acc: 0.6642
Epoch 11/50
390/390 [==============================] - 50s 128ms/step - loss: 0.8699 - acc: 0.6957 - val_loss: 0.9548 - val_acc: 0.6761
Epoch 12/50
390/390 [==============================] - 50s 127ms/step - loss: 0.8420 - acc: 0.7029 - val_loss: 0.8614 - val_acc: 0.7162
Epoch 13/50
390/390 [==============================] - 49s 127ms/step - loss: 0.8167 - acc: 0.7119 - val_loss: 0.9302 - val_acc: 0.6834
Epoch 14/50
390/390 [==============================] - 49s 126ms/step - loss: 0.7871 - acc: 0.7223 - val_loss: 0.9199 - val_acc: 0.6909
Epoch 15/50
390/390 [==============================] - 50s 128ms/step - loss: 0.7649 - acc: 0.7306 - val_loss: 0.9767 - val_acc: 0.6634
Epoch 16/50
390/390 [==============================] - 50s 128ms/step - loss: 0.7466 - acc: 0.7369 - val_loss: 0.9010 - val_acc: 0.6893
Epoch 17/50
390/390 [==============================] - 50s 128ms/step - loss: 0.7195 - acc: 0.7463 - val_loss: 1.0151 - val_acc: 0.6600
Epoch 18/50
390/390 [==============================] - 50s 127ms/step - loss: 0.7123 - acc: 0.7485 - val_loss: 0.7432 - val_acc: 0.7535
Epoch 19/50
390/390 [==============================] - 50s 128ms/step - loss: 0.6930 - acc: 0.7560 - val_loss: 0.7600 - val_acc: 0.7426
Epoch 20/50
390/390 [==============================] - 50s 127ms/step - loss: 0.6743 - acc: 0.7600 - val_loss: 0.7515 - val_acc: 0.7486
Epoch 21/50
390/390 [==============================] - 50s 128ms/step - loss: 0.6600 - acc: 0.7653 - val_loss: 0.7701 - val_acc: 0.7401
Epoch 22/50
390/390 [==============================] - 50s 128ms/step - loss: 0.6443 - acc: 0.7706 - val_loss: 0.7075 - val_acc: 0.7596
Epoch 23/50
390/390 [==============================] - 50s 128ms/step - loss: 0.6336 - acc: 0.7743 - val_loss: 0.8336 - val_acc: 0.7181
Epoch 24/50
390/390 [==============================] - 50s 128ms/step - loss: 0.6258 - acc: 0.7791 - val_loss: 0.7557 - val_acc: 0.7497
Epoch 25/50
390/390 [==============================] - 50s 127ms/step - loss: 0.6159 - acc: 0.7813 - val_loss: 0.7290 - val_acc: 0.7530
Epoch 26/50
390/390 [==============================] - 49s 126ms/step - loss: 0.6006 - acc: 0.7861 - val_loss: 0.7906 - val_acc: 0.7381
Epoch 27/50
390/390 [==============================] - 49s 126ms/step - loss: 0.5842 - acc: 0.7931 - val_loss: 0.6580 - val_acc: 0.7775
Epoch 28/50
390/390 [==============================] - 50s 128ms/step - loss: 0.5879 - acc: 0.7918 - val_loss: 0.8969 - val_acc: 0.7026
Epoch 29/50
390/390 [==============================] - 50s 128ms/step - loss: 0.5718 - acc: 0.7960 - val_loss: 0.7724 - val_acc: 0.7430
Epoch 30/50
390/390 [==============================] - 50s 128ms/step - loss: 0.5694 - acc: 0.7963 - val_loss: 0.7393 - val_acc: 0.7547
Epoch 31/50
390/390 [==============================] - 50s 128ms/step - loss: 0.5622 - acc: 0.7980 - val_loss: 0.6061 - val_acc: 0.8003
Epoch 32/50
390/390 [==============================] - 50s 127ms/step - loss: 0.5461 - acc: 0.8045 - val_loss: 0.6662 - val_acc: 0.7729
Epoch 33/50
390/390 [==============================] - 50s 127ms/step - loss: 0.5502 - acc: 0.8037 - val_loss: 0.6729 - val_acc: 0.7785
Epoch 34/50
390/390 [==============================] - 50s 128ms/step - loss: 0.5408 - acc: 0.8056 - val_loss: 0.6532 - val_acc: 0.7867
Epoch 35/50
390/390 [==============================] - 50s 128ms/step - loss: 0.5301 - acc: 0.8105 - val_loss: 0.7026 - val_acc: 0.7651
Epoch 36/50
390/390 [==============================] - 50s 128ms/step - loss: 0.5233 - acc: 0.8102 - val_loss: 0.7027 - val_acc: 0.7654
Epoch 37/50
390/390 [==============================] - 50s 127ms/step - loss: 0.5168 - acc: 0.8136 - val_loss: 0.6641 - val_acc: 0.7780
Epoch 38/50
390/390 [==============================] - 50s 128ms/step - loss: 0.5223 - acc: 0.8127 - val_loss: 0.6326 - val_acc: 0.7891
Epoch 39/50
390/390 [==============================] - 50s 128ms/step - loss: 0.5083 - acc: 0.8188 - val_loss: 0.6124 - val_acc: 0.7981
Epoch 40/50
390/390 [==============================] - 50s 127ms/step - loss: 0.5000 - acc: 0.8217 - val_loss: 0.6823 - val_acc: 0.7735
Epoch 41/50
390/390 [==============================] - 50s 128ms/step - loss: 0.5003 - acc: 0.8205 - val_loss: 0.6055 - val_acc: 0.7974
Epoch 42/50
390/390 [==============================] - 50s 128ms/step - loss: 0.4880 - acc: 0.8254 - val_loss: 0.7150 - val_acc: 0.7611
Epoch 43/50
390/390 [==============================] - 50s 127ms/step - loss: 0.4847 - acc: 0.8230 - val_loss: 0.6323 - val_acc: 0.7858
Epoch 44/50
390/390 [==============================] - 50s 128ms/step - loss: 0.4802 - acc: 0.8273 - val_loss: 0.6696 - val_acc: 0.7767
Epoch 45/50
390/390 [==============================] - 50s 128ms/step - loss: 0.4747 - acc: 0.8305 - val_loss: 0.6420 - val_acc: 0.7836
Epoch 46/50
390/390 [==============================] - 50s 128ms/step - loss: 0.4758 - acc: 0.8280 - val_loss: 0.6732 - val_acc: 0.7809
Epoch 47/50
390/390 [==============================] - 50s 128ms/step - loss: 0.4655 - acc: 0.8316 - val_loss: 0.6776 - val_acc: 0.7710
Epoch 48/50
390/390 [==============================] - 50s 127ms/step - loss: 0.4684 - acc: 0.8298 - val_loss: 0.6159 - val_acc: 0.7950
Epoch 49/50
390/390 [==============================] - 50s 128ms/step - loss: 0.4616 - acc: 0.8323 - val_loss: 0.6490 - val_acc: 0.7871
Epoch 50/50
390/390 [==============================] - 50s 128ms/step - loss: 0.4587 - acc: 0.8332 - val_loss: 0.5967 - val_acc: ** 0.8029 **
Model took 2492.54 seconds to train

```
