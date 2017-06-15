

Model:
------
The Generative Adversarial Network (GAN) model built in the tensorflow notebook (in this folder) is given by the following image.

![Imgur](http://i.imgur.com/yHCcdsV.jpg)
Notes:
------

Some of the most salient points to keep in mind is how *g_loss*  (generator loss) and *d_loss_fake* (discriminator loss for fake images) are evaluated, although the sources of evaluating these errors are the same tensors, i.e.  *d_model_fake*: discriminator's output for fake images, and *d_logits_fake*: discriminator's output rescaled by using the tf.tanh function.

The difference is highlighted by the following piece of code. For the same output, i.e. *d_logits_fake* it is fed to the generator while making it think those are real images (notice: tf.one_like(...)). The output *d_logits_fake* is fed to the discriminator while letting it know that those are indeed fake images (i.e. tf.zeros_like(...))

    g_loss = tf.reduce_mean(       tf.nn.sigmoid_cross_entropy_with_logits(
       logits=d_logits_fake, labels=tf.ones_like(d_model_fake)))
        
    d_loss_fake = tf.reduce_mean(        tf.nn.sigmoid_cross_entropy_with_logits(
       logits=d_logits_fake, labels=tf.zeros_like(d_model_fake)))


Additionally:
------------
The above contains code to use batch normalization layers for the layers in both the discriminator and the generators. Hopefully in some weeks ahead, we will get a chance to look at it in more detail. For now, it suffices to know that these layers help to normalize the error gradients as we do back-propagation. You can look for more information on this online, or in the following [notebook](https://github.com/apiltamang/deep-learning/blob/master/batch-norm/Batch_Normalization_Exercises.ipynb). There's a lot of excessive information in this notebook, so feel free to skip it, while just focusing on the GAN model.

