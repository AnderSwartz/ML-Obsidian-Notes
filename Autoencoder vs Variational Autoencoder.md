# Autoencoder
Takes in x, generates latent variable z, reconstructs x_hat using z. Goal is to minimize difference b/w x and x_hat

# Variational Autoencoder
Bigger goal of generative modeling: the images (x) are drawn from some underlying data dist. p(x). Goal of generative modeling is to model of p(x). Instead of generating a bunch of outputs (x_hats), generate a bunch of distributions. At the end, instead of having a bunch of single x_hats, you have a combination of all the output distributions
- It defines a distribution p(x) instead of just defining points x


# Use Cases
- Latent embedding for clustering or comparing inputs
- To generate things (after training), throw away encoder. Sample z from p(z) and then generate using decoder. Same as GAN