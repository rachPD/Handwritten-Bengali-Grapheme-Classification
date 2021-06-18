# Handwritten-Bengali-Grapheme-Classification
 Separating the graphemes,  vowel diacritics and consonant diacritics from the Bengali handwritten images.
# Dataset 
The training contained around 0.2 million images origininally supplied as binary vectors in parquet format which were converted to .jpg format for ease. The dimension for every image was originally 137 X 236 . The test set was of approximately same size as that of the training set but it contained several graphemes which had not been supplied in the training set, however the graphemes contained the combination of same roots, vowel diacritics and consonant diacritics.

# Solution Approach
 1. Trained several models of Resnet50, Resnet101, efficientnet b0, b1, b2, b3, SeREsNEXT on Pytorch
 2. Ensembled over the best performing models
 3. Tried Cutmix, Cutout, Fmix - new augmentaion techniques to achieve better generalization and results
 4. Trained 3 separate models for grapheme root, vowel diacritic and consonant diacritic respectively
 5. Trained 1 common model for the entire task treating it as a multi-class classification task
 6. Performed Test Time Augmentations to get better results
 7. Metric used : F1 score
 8. Loss Function : BCE with Logits, Categorical Crossentropy
 9. Optimizers : Adam, Ranger, SGD
