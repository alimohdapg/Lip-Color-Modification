# Lip Color Modifcation System
## Introduction:
This report details how a lip color modification system that utilizes the lip’s facial landmarks is created. Justifications for the system’s design choices are first given before qualitative results are examined to understand the system’s behavior with different types of images.

## Methods:
The lip color modification function uses the output given by a face alignment model’s prediction to identify the location of the lips on the face. The lip’s color is then changed to match what the user inputted. The following flowchart showcases how this is done:

<img width="608" alt="image" src="https://user-images.githubusercontent.com/84683922/184543255-081793a3-d565-4498-a4ff-b53a6f061d01.png">

The following are the parameter justifications for the lip color modification system:
* (5, 5) Kernel size for the morphological close operator - Provides a balance between cleaning up gaps in the lip’s shape and not closing large gaps in between the two lips as that may represent an opened mouth.
* (15, 15) Kernel size for the gaussian blur filter - To factor more values into the average, resulting in a greater blur that adds to the realism of the final output.
* Weighting of 1.0 and 0.5 when combining the original image and lip image respectively - Results in an output that is realistic as the original image’s lip color is taken into account. The rest of the original image is also left unchanged.

## Results & Analysis:

<img width="900" alt="image" src="https://user-images.githubusercontent.com/84683922/184543281-6491c6d8-865f-4eb3-8065-864f224783b4.png">

<img width="900" alt="image" src="https://user-images.githubusercontent.com/84683922/184543297-c0bc0ca9-8292-4e03-954d-0a23bf9e5a13.png">

These qualitative results show how the system works in different types of images:
* Lip is clearly present in a colored image - The color being applied takes into account the original color of the lips in the image, creating a realistic result. 
* Gray-scale images - The new color is fully applied as no other color is factored in. 
* The lip isn’t present - The inferred location from the supplied points is colored. 
* The mouth is open - Except for teeth near the oral commissure, the lips are colored correctly.

## Conclusion:
The report demonstrated how a lip color modification system is created and used. Before then displaying the results acquired from using the system and analyzing how different types of images are modified.

## Appendix:
### Section 1 - Full Code:
See Lip_Color_Modification.ipynb file.


