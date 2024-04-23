GLIPv2: Unifying Localization and Vision-Language Understanding
===
NIPS 2022 / arxiv 22.06
###
GLIPv2 = GLIP + VL understanding (VQA, image captioning…)

![img.png](img.png)

### A Unified VL Formulation and Architecture

![img_1.png](img_1.png)


it is straightforward to add lightweight task-specific heads for various VL tasks.

Following GLIP, GLIP v2 uses the classification-to-matchin g trick to unify detection and grounding.
                 
![img_2.png](img_2.png)

W is the weight matrix of the box classifier

![img_3.png](img_3.png)

their difference is the input text format
object detection : string of concatenated candidate object labels
phrase grounding : natural language sentence

### GLIPv2 Pre-training

![img_4.png](img_4.png)

L_ground : VL reformulation of the object detection task
L_inter : real-word contrastive loss
L_mim : standard masked language modeling loss, proposed in BERT

![img_5.png](img_5.png)

T : target affinity matrix

![img_6.png](img_6.png)

![img_7.png](img_7.png)

![img_8.png](img_8.png)

if a region is annotated as “person”, it should be a positive pair with all “person” phrase in detection type texts.
1. other “person” phrase in the batch is a positive.
2. but, “person” phrase in GT is not use positive.
   because “person” phrase in GT carry contexts that are unique to that image-sentence pair.
