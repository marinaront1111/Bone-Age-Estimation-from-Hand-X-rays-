# Bone Age Estimation from Hand X-rays and Its Performance on Pediatric Wrist Trauma Films

## Abstract

Bone age assessment is used to evaluate growth in children. It is performed on an X-ray of the left hand and wrist, taken in a standard position, which is then assessed manually with the Greulich–Pyle atlas. This is a time-consuming procedure with considerable inter-reader variability. Machine learning models can estimate bone age automatically from these images, which could make the assessment faster and more consistent.

In this project, we will train models to estimate bone age from dedicated hand X-rays and compare a classical machine learning model with a convolutional neural network (CNN). Performance will be measured as the mean absolute error in months.

As an exploratory analysis, we will check the performance of the best model on routine wrist X-rays of children taken for other reasons, such as trauma. These images are not taken for bone age assessment: they show mainly the wrist, are taken in different positions, and may include casts or fractures. They also have no bone age labels, but in healthy children bone age is close to chronological age on average, with a normal variation of about one year. Since children with trauma are generally otherwise healthy, we expect the mean difference between predicted bone age and chronological age to be close to zero, and the spread to be similar to this normal variation, if the model is robust. Larger differences would suggest that the model does not generalise to routine X-rays, and we will explore where and why this happens.

## Dataset

**Training:** [RSNA Pediatric Bone Age dataset](https://www.rsna.org/artificial-intelligence/ai-image-challenge/RSNA-Pediatric-Bone-Age-Challenge-2017): 12,611 hand X-rays of children with bone ages of 0–19 years, labelled with bone age and sex.

**Exploratory testing:** [GRAZPEDWRI-DX dataset](https://figshare.com/articles/dataset/GRAZPEDWRI-DX/14825193): 20,327 wrist X-rays from 6,091 children treated for trauma in Graz, Austria, labelled with chronological age and sex.

## Challenges

- **Different images:** the trauma X-rays show mainly the wrist, are taken in different positions and may include casts, metal or fractures.
- **No bone age labels:** the trauma dataset only has chronological age, recorded in whole years, so the model's accuracy there cannot be measured directly.
- **Different population and hospital:** the children and the X-ray machines are different from the training data, and the Greulich–Pyle standard may not fit every population equally well.
