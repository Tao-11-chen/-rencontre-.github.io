# This is an introduction to Alexnet together with convolutional neural networks

## History of CNN and Introduction of Alexnet

![image](https://s3.bmp.ovh/imgs/2022/01/f3717cf0892d9891.png)
AlexNet is considered one of the most influential papers published in computer vision, having spurred many more papers published employing CNNs and GPUs to accelerate deep learning.As of 2021, the AlexNet paper has been cited over 80,000 times according to Google Scholar.

**Paper**:https://proceedings.neurips.cc/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf

**MyCode**:https://github.com/Tao-11-chen/Alexnet

## Theory and structure of CNN

### Theory
  In general,convolutional neural networks is a combination of Convolutions,Subsampling and Full connection,
  In which Convolutions and subsampling is used to extracting feature and full connection is used to learning.
  It can be trained by BP(Back-propagation) algorithm.

  
  **Advantages**:Compared with traditional NN network,it has:
  - less arguments:convolution is better than normal connection
  - heigher accuracy:better extracted features
  - faster training rate:because of less arguments
    
    
### Structure
#### 1.Convolutional Layer：
Used to extract different input features. Some convolution layers may only extract a small part, such as edge information


From my point of view,one convolutional core is like an small eye,it sweeps the picture and keep some feature of the picture 
by multiply itself with each pixel of the picture.

Usually,one Convolutional layer will have many such eyes(convolution core，called filter)

arguments of convolutional layer:
- core size(F):The eyes above is an matrix actually and it should has a size,usually it has the same height and width and the height is 
an odd number(3×3，9×9....)
- padding(P): While the eye is moving to look the picture,the edge of the picture will be ignored,so we need to padding 0 to the edge of the picture
(0 will not influence the consequence of the eye)
- stride(S): How the eye is moving to look the picture,one by one pixel or step once?
- input channelsize: the input channel number,for example RGB picture has three channels
- output channelsize: output channel number,cus one layer has many eyes and every eye will output it's own consequence 


formula to calculate：
<img src="https://latex.codecogs.com/svg.image?\frac{N&space;&plus;&space;2P&space;-&space;F}&space;S&space;&plus;&space;1&space;=&space;N" title="\frac{N + 2P - F} S + 1 = N" />

In the formula,N is the size of the picture tensor(N * N * 3 for RGB image)


#### 2.Subsampling Layer:
Used to reduce the number of parameters,reducing noice and make the model more robust

- Maxpooling:the max number remains and delete the others:

![image](https://img-blog.csdnimg.cn/20191005144841748.png)

- Avgpooling:calculate the average number to save.

arguments of subsampling layer:
- kernel_size:similar to the fliter of convolution layer,decides how many pixel is framed in a box
- stride:decides how fast the box moves

Noting that it's super parameters do not need to be trained actually,it's fixed


#### 3.full connection Layer:
Used to learn the features extracted by convolution cores,all layers are connected to each other,
theoretically,deeper network can learn more,but when it is over fitting,we should reduce the layers or
adding **dropout** to the connections.

Noting that before putting the consequences of subsampling or convolution layer to the full connection layer,
you should add a flatten layer to make the data one-dimensionally









  
  
