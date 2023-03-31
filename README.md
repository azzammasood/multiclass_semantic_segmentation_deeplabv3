# Multiclass semantic segmentation using DeepLabV3+
Multiclass semantic segmentation using DeepLabV3+. Assign semantic labels to every pixel in an image. The Crowd Instance-level Human Parsing Dataset will be used in this project. It has 38,280 diverse human images. Each image is labeled with pixel-wise annotations for 20 categories, along with instance-level identification.

To capture contextual information, DeepLabv3 employs Atrous Convolution, or Dilated Convolution, at different rates. Atrous Convolution is also known as convolution with holes, and the idea is to "inflate" the kernel which in turn skips some of the points. Basically, the kernel/filter that is being applied is expanded and then convolved with the image. 

The below image is of a standard discrete convolution.
![image](https://user-images.githubusercontent.com/98682258/229191938-5f2b8088-d92a-4a22-aeae-7bc35c6b772b.png)
The formula for the standard discrete convolution is:
![image](https://user-images.githubusercontent.com/98682258/229192166-9fb2a453-0ca0-41ab-bfaa-7f108f731cee.png)
The below image is of the dilated convolution.
![image](https://user-images.githubusercontent.com/98682258/229194246-84da8fd2-7c0d-4063-b346-45c865f8e026.png)
The formula for dilated convolution is:
![image](https://user-images.githubusercontent.com/98682258/229194284-477318aa-a376-4279-a748-eaf711a4d058.png)



Steps:
  1. This project is done in Google Colab.
  2. Download the Crowd Instance-level Human Parsing Dataset for training the model, which has roughly 38000 diverse human images. Each image in CIHP is labeled with pixel-wise annotations for 20 categories, as well as instance-level identification. This dataset can be used for the "human part segmentation" task. Dataset downloaded from a shared google drive link.
  3. 
