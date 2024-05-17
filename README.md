# Predicting Defromation Behaviour of materials Using XGBoost

Previously in my work, I attempted to predict the stress-strain behaviour of material using their deformation properties, in this work I attempted to solve the inverse problem. Upon applying load on materials, it breaks. If we keep on applying load from zero till before it breaks, and then un-load (reduce the load gradually) we get the variation of strain with stress, and the material might not retain its original shape and it deforms to some extent. The 4 properties "Loading Plasticity Value",   "Unloading Plasticity",  "Coefficient Plasticity Depth",  "Coefficient Adhesion" of the materials tells us about the deformation of the material. 

 - Loading Plasticity value: The Loading Plasticity Value is a measure of a material's ability to undergo plastic deformation under an applied load before yielding.
 - Unloading Plasticity: Unloading Plasticity refers to the material's behavior when the load is removed, focusing on the permanent (plastic) deformation that remains.
 - Coefficient Plasticity Depth: The Coefficient Plasticity Depth refer to how plastic deformation varies with depth in a material, especially relevant in surface-treated or layered materials.
 - Coefficient Adhesion: The Coefficient Adhesion is a measure of the adhesive strength between two materials or surfaces.

These propeties helps us to obtain the stress-strain graph of the materials which is the most important charecteristic curve to decide whether the material is fit for a task or not, ex: material for aeroplane wings, space shuttle materials and satellite materials etc.,

Previously in Part-1, I have these material property values and I attempted to find the stress-strain behaviour using their deformation properties so that we can use the stress-strain graph to check for the fitness of the material for any task, the code for that work can be found here [here](https://github.com/pbt12/BTP-1-Prediction-of-Loading-and-Unloading-Charecteristics). 

Inversely, current work aims to find the material with certain deformation properties in order to have a particular stress-strain graph. This greatly helps in areas where we need to find the materials that needs to have a certain stress-strain relation.

We used our own data, which cannot be released publicly. We loaded, preprocessed the data by handling any missing value, normalized the inputs and performed simple feature extraction techniques (dividing the graph coefficients with one another) hoping that will help. Then we trained an **XGBoost** classifier on this dataset and tested on test data.

<p align = 'center'>
  <img src = 'https://github.com/pbt12/BTP-2-Predicting-deformation-behaviour-Using-XGBoost/assets/74967927/00f46e36-fb0f-4ce4-861a-0f7444c4ea06'/>
</p>

Predicted vs actual values plot of our work is shown above, which shows that we were able to achieve good results. However improvement is needed in 'Coefficient of Adhesion'. 

### Future work:

- Future work involves usage of a GAN (Generative Adversarial Network) to sovle the inverse problem.
- We tried to solve the problem using GAN, but since the number of hyperparameters to be tuned are higher(good architecture, learning rates of Generator and discriminator etc.,), we implemented a basic version of GAN and tried with it, but results were not at all convincing, because of lack of time we were unable to complete finish this part.
