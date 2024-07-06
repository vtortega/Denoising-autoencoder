# Denoising images from MNIST data set

The idea here is to test the denoising strategy with autoencoders and experiment with various elements.

We have two models. One small simple model and one bigger, longer and smarter model.

The watermark of choice to noise the images was an "X" of size 5 x 5, and with a function that inserts this X in the image at a random position, we poluted the train and test images with these watermarks and removed them with the Denosing algorithm. 

## The small model

![small_model](https://github.com/vtortega/Denoising-autoencoder/assets/112141870/a06bd6ea-6659-4917-82f0-d914a1a00faa)

## The big model

![big_model](https://github.com/vtortega/Denoising-autoencoder/assets/112141870/14c5cc49-acdf-4b60-9872-9c89fd3893c7)

## Some results 
We have the first line with the original images.
The midle images with the watermarks.
The bottom images after going through the model.

## Small model 

### 15 Epochs, 1 Watermark

![small_15_1mark](https://github.com/vtortega/Denoising-autoencoder/assets/112141870/1ce44761-c03b-4c1e-b48d-1e0e071e3b59)

### 50 Epochs, 1 Watermark

![small_50e_1wm](https://github.com/vtortega/Denoising-autoencoder/assets/112141870/30e17e9e-57c8-4542-8083-0118293553a1)

### 50 Epochs, 5 Watermarks

![small_50e_5wm](https://github.com/vtortega/Denoising-autoencoder/assets/112141870/1d1e23b8-8988-47c0-b8a5-e800c9ca352f)

### 100 Epochs, 10 Watermarks
I didn't understand what happened here. I tried to run at higher epochs and got this. Will come back to investigate
further some time.

![small_100e_10wm](https://github.com/vtortega/Denoising-autoencoder/assets/112141870/6698eacc-e537-4fe1-85ff-58597b6b72bd)

## Big Model
This model took way more time to run, in my system, about 5 minutes per epoch. And it takes way more memory too
Of course it was overkill to this dataset, but we can learn a lot with a exageration.

The big model was 3 orders of magnitutde bigger then the small model.

## 15 Epochs, 1 Watermark

![big_15e_1wm](https://github.com/vtortega/Denoising-autoencoder/assets/112141870/998cfb3f-c0e3-4f19-9434-e333b50a46e9)

### 15 Epochs, 10 Watermarks

![big_15e_10m](https://github.com/vtortega/Denoising-autoencoder/assets/112141870/71aa1383-0c7a-4d5f-a9d1-eee93199337b)

### 2 Epochs, 1 Watermarks
Here we can see how a net can behave badly at weird situations, like 2 epochs.

![big_2e_1wm](https://github.com/vtortega/Denoising-autoencoder/assets/112141870/e7a72f18-31d9-4122-8e83-0e356fab7930)


### 5 Epochs, 10 Watermarks

![big_5e_10m](https://github.com/vtortega/Denoising-autoencoder/assets/112141870/4af9ffcf-c77c-415e-9623-00756b664864)

### 5 Epochs, 20 Watermarks 

![big_5e_20wm](https://github.com/vtortega/Denoising-autoencoder/assets/112141870/b19fa74b-572d-4bfc-b68e-a1db6c3fc195)

### 10 Epochs, 30 Watermarks
This one surprised me, is was really able to remove the watermarks very well, its not easy even for a human.

![big_10e_30wm](https://github.com/vtortega/Denoising-autoencoder/assets/112141870/9f736964-dd63-4196-bd66-4f7b87f527e5)

## Conclusion

Big and smart models are indeed better, way better, who would have thought? 
But at what price? That's an answer only your case will you, but a few learnings that we can take from this is that models are made to be run for a higher number of epochs, the need to make a giant model and run it a few times seems to make little sense in relation to it's costs.

The design of the smaller model could be one of the not so good ones . The making of a better small model and an intermediate one will get a visit soon so to arrive at a better undestanding of which one to choose when the time comes. But for now, that's what I got.
