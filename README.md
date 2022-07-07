Action recognition in trimmed videos is much expensive and time consuming as for that we need to take video frame by frame that obviously generates large scale dataset.
So,it's better to use a new weakly supervised architecture what we call as Untrimmed Net that do not require temporal annotations of data.

**Untrimmed-Net involves four steps:**
1. Clip Sampling:- An action instance usually describes the continuous and coherent motion pattern with a specific intention,which may last for a few seconds and contain no shot changes. However, an untrimmed video often exhibits extremely complex motion dynamics, action instances may only occupy small portions of it. Therefore, our
UntrimmedNet starts with generating short clips from the untrimmed videos, which could serve as action proposals for UntrimmedNet training.

2. Feature extraction module:- After proposal generation, these shot clips are fed into deep networks for feature extraction. These feature representations are utilized to describe the clip visual content and passed to the next layers for action recognition.

3. Classification module:- In the classification module, we aim to classify each clip proposal c into the predefined action categories based on the extracted features    Suppose we have C action classes, we learn a linear mapping to transform the feature representation into a C-dimensional score vector.

4. Selection module:- The selection module aims to select those clip proposals of most probably containing action instances. Here we design two kinds of selection mechanisms for this goal: hard selection based on the principle of multiple instance learning (MIL) and soft selection based on the attention-based modeling. As we shall see in experiments, those two selection method can both well handle the problem of weakly supervised learning.

**References**
1. https://arxiv.org/pdf/1703.03329.pdf
2. https://openaccess.thecvf.com/content_cvpr_2017/papers/Wang_UntrimmedNets_for_Weakly_CVPR_2017_paper.pdf
3. https://www.researchgate.net/publication/314433211_UntrimmedNets_for_Weakly_Supervised_Action_Recognition_and_Detection
4. https://www.di.ens.fr/~fbach/bojanowski14weakly.pdf

**Demo for v_HammerThrow_g23_c05.avi**

![image](https://user-images.githubusercontent.com/69111936/177780162-deccb6a1-fe9f-417f-b10f-73ec58a6801a.png)
