# Diploma Project: Watermark Removal

### Plan

Stage 1

1. Overview of existing methods and research
2. Generate basic dataset. I plan to start with 1-2 standard watermarks on high-resolution images.
3. Prepare a pipeline for testing various models. 

Stage 2

1. Test various existing models and pick up the best one
2. Finetune the model until satisfactory results are achieved on the limited dataset.

Stage 3

1. In case HSE provides extra capacity, it is possible to adapt a model for a wider range of watermarks.
2. Create a web application that will be able to remove watermarks.

### Existing Research Overview

The majority of deep learnig methods that successfully remove watermarks from images use GANs. There exist several articles dedicated to different design of such models. One of the most recent articles 'WDNet: Watermark-Decomposition Network for Visible Watermark Removal' demonstrates impressive results. The framework described in the article includes two steps:  the first is detecting the region that contains the watermark with a decomposition network which predict the parameters of the rectange with a watermark inside,  and the second is cleaning up the region with a refinment network. The proposed method allowed to achieve better results than solutions proposed earier.

Another very interesting method was presented in the article Deep Image Prior. The authors proposed a method to enhance images with using neural networks without actually teaching the network. Their method Deep Image Prior is based on the assumption that the structure of the neural network allows us extract necessary information from image that is then used to clean the image. They feed just one noised picture to the CNN and train it to predict the image. If the network is stopped a bit earlier than when it converges, it is highly probable that the network will generate the image without noise. The method is handy  and easy to implement, as it requires no additional data for training. However, it is not the best method for an online service, as processing one image requires several minutes.
