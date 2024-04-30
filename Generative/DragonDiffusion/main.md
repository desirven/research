![img.png](img.png)

T2I Diffusion is high-quality but, lack of editing ability.
this method allows for 4 edits to be made to either the generated image or the actual image.

- Object moving
- Object resizing
- Object appearance replacement
- Content dragging

## Introduction

- DragGAN
    - this paper propose point-to-point dragging scheme.
    - but it is constrained by the capacity and generalization of GAN model
    - Diffusion based model has higher stability and superior generation quality
      (I don't think the generation quality of diffusion is always better).

 ![img_1.png](img_1.png)


- Prompt-to-Prompt
    - they find the cross-attention map between the feature of word and object has a notable local similarity
    - but this method heavily relying on the design of prompts.
    - and in multi-object scenarios have problem to build correctly local similarity.
    - so Dragon Diffusion aim to explore a more fine-grained editable space.

![img_2.png](img_2.png)

- Dragon Diffusion
    - propose classifier-guidance image editing.
      and study how affect the intermediate feature in diffusion to result image.
    - no fine-tune, no training. like Drag GAN
    - extensive experiments

## Method

this paper wants to change content for editing and preserve other content.

![img_3.png](img_3.png)

The Guidance Branch is Reconstruction process like default LDM.

The Generation Branch is editing process.

To preserve the content of the original image, transferring content information through cross-branch self-attention design.

### DIFT
https://diffusionfeatures.github.io/

The recent work, DIFT(Emergent Correspondence from Image Diffusion, 2306), discovers that the intermediate features of diffusion models have a strong correspondence

![img_4.png](img_4.png)

A “diffusion feature” is a feature in the middle of denoising that is noisy in the image.
And DIFT says Diffusion's U-Net is strong at extracting features from noisy data because it was trained on noisy data.
so they calculate cosine distance between the intermediate feature of source point and all point in the target Diffusion Feature to find the closest point was an exact match.

This method can be used for point-to-point matching between different images.

(I will read this paper soon…)

## Classifier-guidance-based Editing Design

### Dragon Diffusion

![img_5.png](img_5.png)

Both feature of generation and guidance branch are need to have high similarity.
so they want to content appearing in the position of m^gud to appear in the target position m^gen
the optimization goal is to make the similarity in Eq.4 as large as possible.

![img_6.png](img_6.png)

They added “share mask” to preserve uneditable areas.****

![img_7.png](img_7.png)

### Multi-scale Guidance

DIFT says that in U-net's decoder, the second layer contains more semantic information, the third layer contains more geometric information.

![img_8.png](img_8.png)

this paper experiment what DIFT said, this figure is the results.
start denoising from random Gaussin noise, but use cross-branch self-attention design proposed in this paper.
first layer is too high-level to reconstruct the original image accurately.
fourth layer have weak feature correspondence.
second and third layers are more suitable for reconstructing the original image as DIFT say in their paper.

### Implementation Details for Each Application

- Object moving

![img_9.png](img_9.png)

![img_10.png](img_10.png)

![img_11.png](img_11.png)

As a result, the object moved well, but parts of the object preserved in previous position.
so they added Contrastive Loss to avoid this phenomenon.

![img_12.png](img_12.png)

![img_13.png](img_13.png)

But it's not very good at inpainting the previous position.
So, they design Inpainting Loss.

![img_14.png](img_14.png)

- Object resizing

![img_15.png](img_15.png)

![img_16.png](img_16.png)

R: interpolation
C: center croping/expansion

- Appearance replacement

![img_17.png](img_17.png)

replace the appearance between object of **same category.**
(This is only possible if they are in the same category, as it only calculates the average of the feature values)
  
![img_19.png](img_19.png)

- Point dragging

![img_18.png](img_18.png)

In this case, m^gen and m^gud denote the destination and starting points.
but m^share is manually defined.
The gradient guidance comes from Eq.5 with out other specific designs.

![img_20.png](img_20.png)

## Cross-branch Self-attention

In this paper, use DDIM inversion for consistency.
However, it is still challenging to maintain high consistency with DDIM inversion alone.
so, they designed Corss-branch Self-attention.

![img_21.png](img_21.png)

![img_22.png](img_22.png)

W is learnable projection matrices / * refers to the convolution operator

In the generation branch, replace the decoder’s self-attention key and value with the corresponding key and value in the guidance branch.

![img_23.png](img_23.png)

## Experiments

![img_24.png](img_24.png)
           
![img_25.png](img_25.png)
                         
![img_26.png](img_26.png)
