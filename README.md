# Icing

A ML based approach to suggest fashion products to users based on an input image.

# Approach

An implementation of [Complete the Look: Scene-based Complementary Product Recommendation (Kang 2019)](https://arxiv.org/abs/1812.01748)

The goal is to predict the compatibility of a product image with a given scene image. Compatibility is measured both globally and locally. 

Global compatibility is the overall compatibility of the product with the image. A feature vector is extracted from the scene image and the product using resnet. These are embedded using a small feed forward network. Global compatibility is the similarity between the two embeddings.

Local compatibility is the compatibility of the product with the different regions of the scene. The scene image is divided into subregions and a feature vector is extracted from each subregion. We then compute the attention weights of each subregion given the product category. Local compatibility is the weighted sum of the subregion embeddings.