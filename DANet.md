# Deep Attractor Network

## Problem Being Addressed

`Cocktail Party Effect` - humans have taken the ability to concentrate on a single voice while in a crowd of voices for granted. This is not an easy task, some signals would need to be filtered out while others would need to be enhanced. More information on this problem [here](https://en.wikipedia.org/wiki/Cocktail_party_effect).

This task is relatively easy to perform if there are at least the same number of recording devices, or sources, as voices to be separated. Popular algorithms such as the [independent component analysis](https://en.wikipedia.org/wiki/Independent_component_analysis) have been used to separate mixed signals as long as the number of signals is less than or equal to the number of sources. However, when this rule is violated and there is only a single microphone source to record multiple voices or signals, the difficulty increases dramatically. 

Some deep learning algorithms have successfully tackled the single-source problem by using class-based methods. Each speaker to be separated is known and labeled, this is known as a speaker-dependent problem. These solutions are great but another problem arises when the signal sources are unknown, or speaker-independent, these deep learning algorithms break down and are unable to separate the sources. This is the problem being addressed by the Deep Attractor Network.

## First Edition: [Deep Clustering](http://ieeexplore.ieee.org/abstract/document/7471631/)

Deep clustering is a deep learning architecture that uses discriminatively trained embeddings as the basis for clustering. It was first applied to spectrogram segmentation, resulting in impressive results on speaker-independent multi-speaker separation. The authors trained a deep network to assign contrastive embedding vectors to each time-frequency region of a spectrogram. This allowed the network to predict the segmentation labels of the target spectrogram from the input mixed signals. The embedding vectors form a low-rank pairwise affinity matrix that approximates the ideal affinity matrix while enabling faster performance results. Essentially, the mixed audio is investigated to find the time-frequency bins where each individual signal dominates. Once this is known, masks can be constructed to un-mix the original signal.

This clustering is performed by using the indicator **Y** to map each element **i** to one of **C** clusters. Therefore, **YY^T** is a binary affinity matrix that results in `1` if the elements are in the same cluster and `0` if they are in different ones.

### Separation Experiments using Clustering

Data set used included mixed audio with either 2 or 3 speakers, with both same gender mixtures as well as cross gender mixtures. This was created by the authors using utterances from the Wall Street Journal (WSJ0) corpus. A 30 h training set and a 10 h validation set consisting of two-speaker mixtures were generated by randomly selecting utterances by different speakers from the WSJ0 training set si_tr_s, and mixing them at various signal-to-noise ratios (SNR) between 0 dB and 10 dB.

## More explaination to come later.
