# Smart-Waste-Classifier-for-Germany-s-Recycling-System-using-Neural-Networks

This project utilizes a neural network to classify waste into nine categories: household waste, electronics, clothing, glass, plastics, paper, organic waste, batteries, and hazardous materials. The primary motivation behind this initiative is to teach expats who are new to Germany how to correctly sort their trash, as the recycling system can be quite complex. 

Drawing from my own experience of navigating waste management when I first arrived in Germany, I found it challenging to identify the appropriate disposal methods for different items. Some waste, such as TVs and hazardous materials, must be taken to special facilities, while other items simply need to go in specific bins. This classifier aims to simplify the process by helping users accurately determine the correct bin or disposal method for each item. Ultimately, the goal is to promote proper recycling and sustainability in Germany through effective waste sorting, making it easier for foreigners to adapt to local practices.

## Resources Used

**Python Version**: 3.12.1

**Packages**: numpy,matplotlib,tensorflor.keras,os, imghdr,cv2

## Data Collection and Data Cleaning

Pictures from the 9 different categories were collected from google pictures, downloading them with the expension "Download All Images". The dataset contains more than 1000 pictures.
Some pictures that had non-compatible formats could be eliminated by hand, as well as pictures under 10KB and unrelated pictures that add noise to the analysis.
I was struggling to run the dataset at the beginning for two reasons:
 * There were still pictures that for whatever reason were problematic or corrupted
 * I kept on getting an UTF-8 error since the original names of the pictures contained Non-ASCII characters.
The first problem was solved by coding an identifier that found these corrupted pictures and then deleted them, and the second issue was solved by another piece of code that renames all the pictures by consecutive numbers


