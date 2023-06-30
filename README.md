# Image-segmentation-Pytorch
Project involving Image Segmentation on a dataset consisting of 300 images of humans with corresponding binary masks for each image. This project aimed to perform segmentation tasks using deep learning techniques.

To access the original dataset, please visit the GitHub repository of the dataset's original author: https://github.com/VikramShenoy97/Human-Segmentation-Dataset

This project is available on Coursera as "Deep Learning with PyTorch: Image Segmentation" and can be accessed directly by visiting the following URL: https://www.coursera.org/projects/deep-learning-with-pytorch-image-segmentation.

The main tasks involved in this project were as follows:
- Understanding the Segmentation Dataset and creating a custom dataset class specifically designed for handling image-mask datasets.
- Applying segmentation augmentation techniques to augment both the images and their corresponding masks. For image-mask augmentation, the Albumentations library was utilized.
- Loading a pretrained state-of-the-art convolutional neural network, such as Unet, for the segmentation problem. This was achieved using the segmentation model PyTorch library.
- Creating a train function and an evaluator function to be used in the training loop. The training loop was responsible for training the model on the dataset.

![image](https://github.com/jose-zerna/Image-segmentation-Pytorch/assets/92068963/e453ef77-c561-45a1-a0ef-e697bc2277f7)

### Bugs and errors obtained during this project:

- **Height and Width of image, mask or masks should be equal:** This error occurred when applying augmentations to the images and masks. The error message suggested that the height and width of the images or masks were not consistent. To address this issue, I disabled the shape check by setting the parameter *is_check_shapes=False* in the Compose class. It is important to note that disabling the shape check should only be done if you are confident about the consistency of your data.
- **Bool value of Tensor with more than one value is ambiguous in Pytorch:**  Another error was encountered due to a missing pair of parentheses when using the *torch.nn.BCEWithLogitsLoss* function. Instead of writing *loss2 = nn.BCEWithLogitsLoss(logits, masks)*, which resulted in an ambiguous bool value error, the correct syntax is *loss2 = nn.BCEWithLogitsLoss()(logits, masks)*. The addition of the parentheses after BCEWithLogitsLoss ensures proper function invocation and resolves the issue.
