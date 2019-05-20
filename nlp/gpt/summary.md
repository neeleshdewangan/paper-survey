#### Paper
- Link:
- Author:
- Conference:

#### Outline
- [ ] Abstract
- [ ] Introduction
- [x] Framework
- [ ] Results
- [ ] Conclusion
- [ ] Research Background
- [ ] What to read next

#### Framework
- Unsupervised Pre-training: (Language Modeling)
  - Standard Language Modelling with Transformers.
  - Used Multilayered Transformer Decoder [34] for language training.
    - Multilayer Transformer Decoder ??
<div class="image-with-text">
  <img src="images/language-model-transformer.png" width="50%" height="75%">
  <p> ( W_e: embedding matrix, W_p: position embedding, U: context vector ) </p>
</div>

  - training objective:
<div class="image-with-text">
  <img src="images/language-model-objective.png" width="30%" height="30%">
  <p> ( W_e: embedding matrix, W_p: position embedding, U: context vector ) </p>
</div>

- Supervised fine tuning
  - Use output of transformer block from last unsupervised pre-training
  - Task specific transfer learning with labelled dataset using **softmax activation** (or non linear activation).
  - Maximize likelihood of the label.
<div class="image-with-text">
  <img src="images/sup-training.png" width="30%" height="30%">
  <p> ( h_l: output of pre-trained transformer, W_y: dense layer weight matrix) </p>
</div>

  - Loss
<div class="image-with-text">
  <img src="images/loss-sup.png" width="30%" height="30%">
</div>

- Auxiliary objective function for optimization:
  - Previous work [50, 43] ??
<div class="image-with-text">
  <img src="images/final-loss.png" width="30%" height="30%">
</div>

- Task Specific Input Transformation or Preprocessing
  - Put Some Delim(e.g. $) between premise p and hypothesis h. 
