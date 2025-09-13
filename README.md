# CV212-Zero-Shot-Object-Detection-Project
In this project me and my group have made zero shot object detection where in code we have libraries import cv2 , numpy , pytesseract , PIL , CLIP , torch
I have used CLIP (Contrastive language image pretraining) model where it starts with detecting areas of objects in an image and then for each region it detects similar patterns to get an image with respect to prompts and it checks with dynamic threshold values and after that it uses tesseract which acts as an OCR (Optical Character Recognition tool) that draws detection box and text box on output box (result)

How code works
In function run_ocr it will first convert PIL image into array for pytesseract and then it will get dictonary with list like top , width etc then it will loop with n boxes so that high confidence values can be appended
