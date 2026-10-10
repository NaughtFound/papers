## Why I read it
Explainability is one of my research interests, and Grad-CAM is the baseline every new method gets compared with.

## The idea
Weight each feature map of a chosen layer by the average gradient of the class score, sum them, and keep the positive part. The result is a coarse heatmap over the image.

## Caveat
Sanity checks later showed that some saliency methods barely change when model weights are randomised. Always run those checks before trusting a map.
