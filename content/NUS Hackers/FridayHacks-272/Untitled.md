Financial data is complex and hard to obtain(high-quality, labeled) and heavily regulated and have biases/imbalances
Solution: synthetic data

### Methods
Systematic review: identify robust approaches. ex. PRISMA
Algorithm Evaluation: 

#### GAN (Generative Adversarial Network)
Generator: creates synthetic data
Discriminator: judges whether real or fake
Standard GAN is not stable, WGAN/CTGAN/DGAN is used
##### CTGAN
Uses conditions
Improves control
##### DGAN
normalize data
creates multiple samples at once

#### Non-GAN
##### Temporal Variational Autoencoder (TVAE)
Compress input then reconstructs sequence
Looks at data before and after
Spots anomalies and outliers
Handles mising data
Less realistic data compared to GANs

##### Financial Tabular Diffusion (FinDiff)
Can handle mixed data types
More stable training process
Better for small/imbalanced datasets
Computationally intensive
unlike GAN, no instability, no mode collapse

Privacy - use DGAN
Fraud detection/risk assessment - non-GAN

User TVAE to create more fraudulent transactions(if too little) for AI models to detect