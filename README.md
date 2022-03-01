# deeplabcut-social-interaction

This is an application that cleans and wrangles the output from pose estimation using DeepLabCut and produces a CSV file containing social exploration information from recordings of the rodent social interaction test. We include a feature that allows for live video analysis of the social interaction test and it can also produce a CSV file containing all the empirical information for each trial. The live video analysis feature provides a visual aid to help researchers see what is being considered a sniff bout. Additionally, the live video analysis results are highly correlated with the results given from DeepLabCut.

At this time, this application is adapted to the Eisch Lab's rodent social interaction protocol where the SI test is performed on two laterally adjacent arenas within 1 trial where only the test mouse in each arena (left and right) arena is detected. 

The validated deeplabcut model was trained on 200 frames that spanned across 4 videos containing arenas side by side. Selected body points of the test mouse were ears, snout and tailpoints, with four aditional points marking the perimeter of the cage containing the social stimulus. The validated model was trained for 200,000 iterations and has around a 95% accuracy.

This project was inspired by papers such as [Nagai, M., Nagai, H., Numa, C. et al. "Stress-induced sleep-like inactivity modulates stress susceptibility in mice"](https://www.nature.com/articles/s41598-020-76717-8?proof=t#citeas) and [Worley, Nicholas B., et al. “Deeplabcut Analysis of Social Novelty Preference.”](https://www.biorxiv.org/content/10.1101/736983v1)

## Some Pictures of the Application
![](images/main.PNG) ![](images/accuracy.PNG) 
![](images/extract_frames.PNG) ![](images/social_interaction.PNG) 
![](social_interaction_gif.gif) 

## Modules
```
cv2
cvzone
glob
math
literal_eval
numpy
os
pandas
re
tkinter
tkinter.filedialog
webbrowser
```

## Installation
#python 3.9 🐍
```
pip install opencv-python
pip install cvzone
pip install pandas
```

## Files
### main.py
```
Creates the GUI and calls on the other files for functions.
```
### accuracy.py
```
This file calculates the accuracy of the model on the video by calculating the amount of dropped frames in the video.
```
### social_interaction.py
```
This file produces a CSV that contains empirical information about the social interaction test, such as sniff count 
and sniff time in seconds.
```
### extract_frames.py
```
This file extracts frames in the video to use as a reference and produces live video analysis of the social interaction
test. Additionally, it can produce a CSV file that shows all the sniff counts and sniffle time for all trials.
```
### interaction_zone.py
```
This file produces a CSV that contains information on mice activity within a designated interaction zone. This interaction
zone is the area that's 9cm from the arena corners and 14 cm outward.
```
