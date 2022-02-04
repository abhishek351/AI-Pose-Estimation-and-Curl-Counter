# AI-Pose-Estimation-and-Curl-Counter

## Overview
A biceps curl counter based on human pose estimation. The idea is to make the user aware of inaccurate range of motion in real-time so that he/she can correct it immediately without the need of a human exercising partner. Often as a novice, we are dealing with incorrect exercising postures which eventually leads to no gain or in the worst conditions, unwanted damage and tear to the muscles.

The counter doesn't tick if the range of motion during a bicep curl is within 40 degrees and 160 degrees. Hence to get the counter going, user has to curl and uncurl his/her biceps in a full range of motion. No cheating now!


Pose Landmark Model (BlazePose GHUM 3D)
The landmark model in MediaPipe Pose predicts the location of 33 pose landmarks (see figure below).


![pose](https://user-images.githubusercontent.com/70373142/152560248-1f23beb5-d1aa-424b-a500-8ebcf080af3d.png)



## Description
The project is based on Mediapipe's Pose Estimation Model [Blazepose](https://arxiv.org/abs/2006.10204) at the backend which is responsible for calculating the 3D coordinates of the human body keypoints. We then extract the three: wrist, elbow and shoulder keypoints and form two straight lines joning shoulder and elbow(A) / elbow and wrist(B). Calculating the angle between the two straight lines A and B gives us the angle formed at elbow of the hand which is then used for counter increments. A binary variable 'flag' is responsible for maintaining the position of the hand during curls; UP or DOWN. A successful transition of the hand from DOWN to UP increases the counter by 1 each time. Separate counters are maintained for right and left hands.


## Future Improvements:
* Inclusion of custom range of motion which is currently fixed between between 40 degrees and 160 degrees so that user can use it for different forms of curls.
* Add Deadlift and many other exercises. 




