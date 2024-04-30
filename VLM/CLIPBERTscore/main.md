![img.png](img.png)

![img_1.png](img_1.png)

they want to measuring both relation of image-text and text-summarization.
It’s weighted combination of their proposed CLIPBERT score.

1. they propose multimodal summarization metric based on a combination of CLIPScore and BERTScore

2. create MuFaME benvhmark

3. present detailed study of their metric and factuality metric evaluation banchmarks and present strong empirical evidence of its robustness

4. demonstrate two useful dowstream

    a. Multimodal Visual Guidancechoose a picture that best represents description

    b. Self-Critical Sequence Training with CLIPBERTscore Rewardoffer clipbertscore as a reward for reinforcement learning



* Multimodal Factuality Meta-Evaluation (MuFaME) benchmark

they use WikiHow summarization dataset.
this dataset has been extensively studied for document summarization.

Summarization model

document summarization model : T5, PEGASUS
multimodal summarization model : CLIP-BART, MOF

* Human judgments


![img_2.png](img_2.png)


They used AMT to prove the validity of their metrics.

![img_3.png](img_3.png)

* WikiHow Factuality task

they propose this task that evaluates how well the metric can choose the correct summaries over incorrect ones.
 
![img_4.png](img_4.png)

![img_5.png](img_5.png)
