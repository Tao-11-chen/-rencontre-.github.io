# This is an introduction to Alexnet together with convolutional neural networks

## 1.History of CNN and position of Alexnet

## 2.Theory and structure of CNN

### 1.Theory
  In general,convolutional neural networks is a combination of Convolutions,Subsampling and Full connection,
  In which Convolutions and subsampling is used to extracting feature and full connection is used to learning.
  It can be trained by BP(Back-propagation) algorithm.

  
  **Advantages**:Compared with traditional NN network,it has:
  - less arguments:convolution is better than normal connection
  - heigher accuracy:better extracted features
  - faster training rate:because of less arguments
    
    
### 2.structure
#### Convolutional Layer：
Used to extract different input features. Some convolution layers may only extract a small part, such as edge information


From my point of view,one convolutional core is like an small eye,it sweeps the picture and keep some feature of the picture 
by multiply itself with each pixel of the picture.

Usually,one Convolutional layer will have many such eyes(convolution core，called filter)

arguments of convolutional layer:
- core size:The eyes above is an matrix actually and it should has a size,usually it has the same height and width and the height is 
an odd number(3×3，9×9....)
- padding: While the eye is moving to look the picture,the edge of the picture will be ignored,so we need to padding 0 to the edge of the picture
(0 will not influence the consequence of the eye)
- stride: How the eye is moving to look the picture,one by one pixel or step once?
- input channelsize: the input channel number,for example RGB picture has three channels
- output channelsize: output channel number,cus one layer has many eyes and every eye will output it's own consequence 
- 
  
  
