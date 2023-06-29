# Image-segmentation-Pytorch
This project consists on performing Image Segmentation to a dataset that contains 300 images of humans with some background and a corresponding binary mask for each of these images

This is a guided project from Coursera: https://www.coursera.org/projects/deep-learning-with-pytorch-image-segmentation
Original author of the dataset : https://github.com/VikramShenoy97/Human-Segmentation-Dataset

These were the major tasks that the project involved:

- Understand the Segmentation Dataset and write a custom dataset class for Image-mask dataset.
- Apply segmentation augmentation to augment images as well as its masks. For image-mask augmentation albumentation library was used.
- Load a pretrained state of the art convolutional neural network for segmentation problem(for e.g, Unet) using segmentation model Pytorch library.
- Create train function and evaluator function for using when writing training loop. Use training loop to train the model.

![image](https://github.com/jose-zerna/Image-segmentation-Pytorch/assets/92068963/e453ef77-c561-45a1-a0ef-e697bc2277f7)

### Bugs and errors obtained during this project:

- **Height and Width of image, mask or masks should be equal:** You can disable shapes check by setting a parameter *is_check_shapes=False of Compose class (do it only if you are sure about your data consistency)*. This error was obtained while applying augmentation to the images and masks. I avoided this by adding *is_check_shapes=False* to avoid shape checking.1
- **Bool value of Tensor with more than one value is ambiguous in Pytorch:** This error was obtained because I missed the parenthesis using the *torch.nn.BCEWithLogitsLoss* function. I wrote *loss2 = nn.BCEWithLogitsLoss(logits , masks)* instead of *loss2 = nn.BCEWithLogitsLoss()(logits , masks)*.
