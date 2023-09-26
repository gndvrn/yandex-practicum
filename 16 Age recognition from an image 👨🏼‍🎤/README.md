# Age recognition from an image 👨🏼‍🎤

For a supermarket with a rather "tasty" name "Bread-Salt", we were tasked with developing a neural network model to determine the age of customers based on their photos. We successfully completed this task (taking into account technical requirements).

## Brief summary of completed tasks

### Step 1. Data overview

- Imported libraries;
- Loaded data. `ImageDataGenerator` was used to form batches with images;
- Studied information about the data;
- Examined the visual content of the first 25 images from the first batch;
- Evaluated the distribution of values of the target feature.

### Step 2. Model training

As the main model, we chose the `ResNet50` model, pre-trained on the ImageNet image dataset. To improve the quality of predictions, the following layers were added to the main model:

- `GlobalAveragePooling2D`. A convolutional layer for reducing the size of the entire output tensor of the main model;
- `Dropout`. A layer for regularization that reduces overfitting by excluding complex connections between neurons of previous layers of the network.
- `Dense`. The final layer of the neural network model that uses the ELU activation function. Why not ReLU? ReLU transforms all input values obtained into 0, so these values are not taken into account in the next layer, while ELU uses an exponential function to determine the values of the previous layer that are equal to zero ⇒ we get more significant features for solving the set task in the end.

✅ On the test set, the `MAE` value was equal to `6.05`, which satisfies the customer's technical requirements.
