# Multiclass semantic segmentation using DeepLabV3+
Multiclass semantic segmentation using DeepLabV3+, which is, in a nutshell, a combination of Encoder-Decoder with Spatial Pyramid Pooling. Assign semantic labels to every pixel in an image. The Crowd Instance-level Human Parsing Dataset will be used in this project. It has 38,280 diverse human images. Each image is labeled with pixel-wise annotations for 20 categories, along with instance-level identification.

## Theory

**How DeepLab works**: 
1. Atrous Convolution is also known as convolution with holes, and the idea is to "inflate" the kernel which in turn skips some of the points. Basically, the kernel/filter that is being applied is expanded and then convolved with the image. By this, we can control the resolution of features computed by deep convolutional neural networks and adjust filter’s field-of-view in order to capture multi-scale information.
2. Atrous Spatial Pyramid Pooling probes the incoming convolutional feature layer with filters at multiple sampling-rates and effective fields of view, thus capturing objects as well as image context at multiple scales. 
3. Improve the localization of object boundaries by combining the responses at the final DCNN layer with a fully connected Conditional Random Field (CRF).

To capture contextual information, DeepLabv3 employs several parallel Atrous Convolution, or Dilated Convolution, at different rates (called Atrous Spatial Pyramid Pooling). Even though rich semantic information is encoded in the last feature map, detailed information related to object boundaries is missing due to the pooling or convolutions with striding operations within the network backbone. 

The below image is of a standard discrete convolution.

![image](https://user-images.githubusercontent.com/98682258/229191938-5f2b8088-d92a-4a22-aeae-7bc35c6b772b.png)

The formula for the standard discrete convolution is:

![image](https://user-images.githubusercontent.com/98682258/229192166-9fb2a453-0ca0-41ab-bfaa-7f108f731cee.png)

The below image is of the dilated convolution.

![image](https://user-images.githubusercontent.com/98682258/229194246-84da8fd2-7c0d-4063-b346-45c865f8e026.png)

The formula for dilated convolution is:

![image](https://user-images.githubusercontent.com/98682258/229194284-477318aa-a376-4279-a748-eaf711a4d058.png)

Where l is known as the dilation rate (widening of kernel), and l=1 equals standard discrete convolution.

**How DeepLabv3 works**:
DeepLabv3+, extends DeepLabv3 by adding a simple yet effective decoder module to recover the object boundaries. The backbone network is used to extract features from the input image. The ASPP module is then applied to the output of the backbone network to capture multi-scale context information. It consists of multiple parallel atrous convolutional layers with different dilation rates, which allow the network to capture context information at different scales. Finally, the decoder network is used to upsample the output of the ASPP module to the same size as the input image, producing the final semantic segmentation map. 

![image](https://user-images.githubusercontent.com/98682258/229280717-eb1febc8-2021-4fb8-b2ea-ade041417db8.png)

Steps:
  1. This project is done in Google Colab.
  2. Download the Crowd Instance-level Human Parsing Dataset for training the model, which has roughly 38000 diverse human images. Each image in CIHP is labeled with pixel-wise annotations for 20 categories, as well as instance-level identification. This dataset can be used for the "human part segmentation" task. Dataset downloaded from a shared google drive link.
  3. 
