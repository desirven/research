## 매일 읽는 논문을 기록하기 위한 레포
### contribution 위주로 정리

## TODO
> vq diffusion (https://arxiv.org/abs/2111.14822) </br>
> Improved vq diffusion (https://arxiv.org/abs/2205.16007) </br>
> Resolution-robust Large Mask Inpainting with Fourier Convolutions </br>
> TF-ICON </br>
> GPT-V (https://cdn.openai.com/papers/GPTV_System_Card.pdf)  </br>

> ICCV 2023 </br>
> * A_Latent_Space_of_Stochastic_Diffusion_Models_for_Zero-Shot_Image
> * BoxDiff_Text-to-Image_Synthesis_with_Training-Free_Box-Constrained_Diffusion
> * DiffuMask_Synthesizing_Images_with_Pixel-level_Annotations_for_Semantic_Segmentation_Using
> * Diffusion_Models_as_Masked_Autoencoders
> * DiffusionDet_Diffusion_Model_for_Object_Detection
> * Discriminative_Class_Tokens_for_Text-to-Image_Diffusion_Models
> * Editing_Implicit_Assumptions_in_Text-to-Image_Diffusion_Models
> * End-to-End_Diffusion_Latent_Optimization_Improves_Classifier_Guidance
> * Improving Sample Quality of Diffusion Models Using Self-Attention Guidance
> * Localizing_Object-Level_Shape_Variations_with_Text-to-Image_Diffusion_Models
> * Versatile_Diffusion_Text_Images_and_Variations_All_in_One_Diffusion

------
## Done (JIRA에서 여기로 이사중)
| Name                                                                                                                                          | Keyword                  | Publish    | arxiv  | ...              |
|-----------------------------------------------------------------------------------------------------------------------------------------------|--------------------------|------------|--------|------------------|
| [GLIDE](./Generative/GLIDE/GLIED.md)                                                                                                          | Inpainting               | ICML 2021  | 21.12  |                  |
| [DALLE2](./Generative/DALLE2/DALLE2.md)                                                                                                       | Text2Image               |            | 22.04  |                  |
| [DALLE3](./Generative/DALLE3/DALLE3.md)                                                                                                       | Text2Image               |            | 23.09? |                  |
| [Blended Diffusion](./Generative/Blended_Diffusion/Blended_Diffusion.md)                                                                      | Inpainting               | CVPR 2022  | 21.11  |                  |
| [Bledned_Latent_Diffusion](./Generative/Bledned_Latent_Diffusion/Bledned_Latent_Diffusion.md)                                                 | Inpainting               | ACM 2022   | 22.06  |                  |
| [text2live](./Generative/text2live/text2live.md)                                                                                              | Image Blending           | ECCV 2022  | 22.04  |                  |
| [zoom-to-inpaint](./Generative/zoom-to-inpaint/zoom-to-inpatint.md)                                                                           | Inpainting               | CVPRW 2022 | 20.12  |                  |
| [Differential Diffusion: Giving Each Pixel Its Strength](./Generative/Differential_Diffusion/Differential_ddifusion.md)                       | Inpainting               |            | 23.06  |                  |
| [All are Worth Words: A ViT Backbone for Diffusion Models](./Generative/All_are_Worth_Words/All_are_Worth_Words.md)                           | Diffusion                | CVPR 2022  | 22.09  |                  |
| [Foreground-Background Separation through Concept Distillation from](./Generative/Foreground-Background_Separation/main.md)                   | Segmentation             | ICCV 2023  | 22.12  |                  |
| [MagicFusion: Boosting Text-to-Image Generation Performance by Fusing Diffusion Models](./Generative/MagicFusion/main.md)                     | Diffusion Ensemble       | ICCV 2023  | 23.03  |                  |
| [Unleashing Text-to-Image Diffusion Models for Visual Perception](./Generative/Visual_Perception_Diffusion/main.md)                           | Segmentation             | ICCV 2023  | 23.03  |                  |
| [Null-text Inversion for Editing Real Images using Guided Diffusion Models](./Generative/Null-text_Inversion/main.md)                         | Inversion                | CVPR 2023  | 22.11  |                  |
| [DASO: Distribution-Aware Semantics-Oriented Pseudo-label for Imbalanced Semi-Supervised Learning](./Generative/Semi-Supervised/DASO/main.md) | SSL, CLS                 | CVPR 2022  | 21.06  |                  |
| [DiffusinoCLIP: Text-Guided Diffusion Models for Robust Image Manipulation](./Generative/DiffusionCLIP/main.md)                               | Inversion                | CVPR 2022  | 21.10  |                  |
| [Prompt Tuning Inversion for Text-Driven Image Editing Using Diffusion Models](./Generative/Prompt_Tuning_Inversion/main.md)                  | Inversion                | ICCV 2023  | 23.05  |                  |
| [Editing Implicit Assumptions in Text-to-Image Diffusion Models](./Generative/Editing_Implicit_Assumptions/main.md)                           | Model Editing            | ICCV 2023  | 23.03  |                  |
| [DiffusionCLIP: Text-Guided Diffusion Models for Robust Image Manipulation](./Generative/DiffusionCLIP/main.md)                               | Inversion                | CVPR 2022  | 21.10  | DDIM Inversion   |
| [MAG-Edit: Localized Image Editing in Complex Scenarios via Mask-Based Attention-Adjusted Guidance](./Generative/MAG-Edit/main.md)            | Inpainting               |            | 23.12  |                  |
| [DreamInpainter: Text-Guided Subject-Driven Image Inpainting with Diffusion Models](./Generative/DreamInpainter/main.md)                      | Inpainting, Personalized |            | 23.12  |                  |
| [Attend-and-Excite: Attention-Based Semantic Guidance for Text-to-Image Diffusion Models](./Generative/Attend-and-Excite/main.md)             | Text align               | ACM 2023   | 23.01  |                  |
| [DALL-E for Detection: Language-driven Compositional Image Synthesis for Object Detection](./Generative/DALL-E_for_Detection/main.md)         | Synthetic data for OD    |            | 22.06  |                  |
| [Dreambooth](./Generative/DreamBooth/main.md)                                                                                                 | Personalized             | CVPR 2022  | 22.08  |                  |
| [DiffusionClassifier](./Generative/DiffusionClassifier/main.md)                                                                               | Classification           | ICCV 2023  | 23.03  |                  |
| [X-Paste: Revisiting Scalable Copy-Paste for Instance Segmentation using CLIP and StableDiffusion](./Generative/X-Paste/main.md)              | Synthetic data for SG    | ICML 2022  | 22.12  |                  |
| [DiffusionEngine: Diffusion Model is Scalable Data Engine for Object Detection](./Generative/DiffusionEngine/main.md)                         | Synthetic data for OD    |            | 23.09  |                  | 
| [PHOTOSWAP: Personalized Subject Swapping in Images](./Generative/PhotoSwap/main.md)                                                          | Personalized             | NIPS 2023  | 23.05  | 내용 부실함           |
| [Adding Conditional Control to Text-to-Image Diffusion Models](./Generative/ControlNet/main.md)                                               | Fintuning Diffusion      | ICCV 2023  | 23.02  | 내용 부실함           |
| [Estimation of Non-Normalized Statistical Models by Score Matching](./Generative/ScoreMatching/main.md)                                       | Score-based              | MLR 2005   |        |                  |
| [Shape-Guided Diffuion with Inside-Outside Attention](./Generative/Shape-Guided_Diffusion/main.md)                                            | Inpainting               |            | 22.12  |                  |
| [Compositional Visual Generation with Composable Diffusion Models](./Generative/ComposableDiffusion/main.md)                                  | Compose condition        | ECCV 2022  | 22.06  |                  |
| [SmartMask: Context Aware High-Fidelity Mask Generation for Fine-grained Object Insertion and Layout Control](./Generative/SmartMask/main.md) | Inpainting               |            | 23.12  | |
| [Guided Image Synthesis via Initial Image Editing in Diffusion Model](./Generative/Guided_Initial_Image_Editing/main.md)                      | Image Editing            | ACMMM 2023 | 23.05  | Initial Noise    |
| [Pretraining is All You Need for Image-to-Image Translation](./Generative/Pretraining_for_I2I_Translation/main.md)                            | I2I translation          |            | 22.05  |                  |
| [InstructPix2Pix: Learning to Follow Image Editing Instructions](./Generative/InstructPix2Pix/main.md)                                        | I2I translation          | CVPR 2022  | 22.11  |                  |
| HyperNetworks                                                                                                                                 |                          |            |        |                  |
| Prompt-to-Prompt                                                                                                                              |                          |            |        |                  |
| EDICT                                                                                                                                         |                          |            |        |                  |
| Null-text Inversion                                                                                                                           |                          |            |        |                  |
| Fader Networks                                                                                                                                |                          |            |        |                  |
| MasaCtrl                                                                                                                                      |                          |            |        |                  |
| On Distillation of Guided Diffusion Models                                                                                                    |                          |            |        |                  |
| Classifier-Free Diffusoin Guidance                                                                                                            |                          |            |        |                  |
| GLIP                                                                                                                                          |                          |            |        |                  |
| Generate Anything Anywhere in Any Scene                                                                                                       |                          |            |        |                  |
| Semantic Object Accuracy for Generative Text-to-Image Synthesis                                                                               |                          |            |        |                  |
| GLIGEN                                                                                                                                        |                          |            |        |                  |
| JourneyDB                                                                                                                                     |                          |            |        |                  |
| Drag Your GAN                                                                                                                                 |                          |            |        |                  |
| DragDiffusion                                                                                                                                 |                          |            |        |                  |
| DragonDiffusion                                                                                                                               |                          |            |        |                  |
| CLIP know about a red circle?                                                                                                                 |                          |            |        |                  |
| ReVersion                                                                                                                                     |                          |            |        |                  |
| BERT score                                                                                                                                    |                          |            |        |                  |
| Evaluating and Improving Factuality in Multimodal Abstractive Summarization                                                                   |                          |            |        |                  |
| LDM                                                                                                                                           |                          |            |        |                  |
| StableRep                                                                                                                                     |                          |            |        |                  |
| ImageBrush                                                                                                                                    |                          |            |        |                  |
| GLIP v2                                                                                                                                       |                          |            |        |                  |
| Generative Modeling by Estimating Gradients of the Data Distribution                                                                          |                          |            |        |                  |
| LoRA                                                                                                                                          |                          |            |        |                  |
| IMAGEN</br>Photorealistic Text-to-Image Diffusion Models with Deep Language Understanding                                                     |                          |            |        |                  |
| An Edit Friendly DDPM Noise Space: Inversion and Manipulations                                                                                |                          |            |        |                  |
| Unifying Diffusion Models' Latent Space, with Applications to CycleDiffusion and Guidance                                                     |                          |            |        |                  |
| AnyDoor                                                                                                                                       |                          |            |        |                  |
| LEDITS                                                                                                                                        |                          |            |        |                  |
| SEGA                                                                                                                                          |                          |            |        |                  |
| Collage Diffusion                                                                                                                             |                          |            |        |                  |
| DiffEdit                                                                                                                                      |                          |            |        |                  |
| Paint by Word                                                                                                                                 |                          |            |        |                  |
| Improving Sample Quality of Diffusion Models Using Self-Attention Guidance                                                                    |                          |            |        |                  |
| DALLE-2 is Seeing Double: Flaws in Word-to-Concept Mapping in Text2Image Models                                                               |                          |            |        |                  |
| CoCa                                                                                                                                          |                          |            |        |                  |
| T2I-CompBench                                                                                                                                 |                          |            |        |                  |
| Clipscore                                                                                                                                     |                          |            |        |                  |
| SmartBrush                                                                                                                                    |                          |            |        |                  |
| ILVR                                                                                                                                          |                          |            |        |                  |
|                                                                                                                                               |                          |            |        |                  |
