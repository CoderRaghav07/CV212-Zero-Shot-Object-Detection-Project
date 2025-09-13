# CV212-Zero-Shot-Object-Detection-Project
In this project me and my group have made zero shot object detection where in code we have libraries import cv2 , numpy , pytesseract , PIL , CLIP , torch
I have used CLIP (Contrastive language image pretraining) model where it starts with detecting areas of objects in an image and then for each region it detects similar patterns to get an image with respect to prompts and it checks with dynamic threshold values and after that it uses tesseract which acts as an OCR (Optical Character Recognition tool) that draws detection box and text box on output box (result)

How code works
In function run_ocr it will first convert PIL image into array for pytesseract and then it will get dictonary with list like top , width etc then it will loop with n boxes so that high confidence tokens can be appended and will be returned

In function non_max_supression it will remove overlapping duplicate detection boxes and will keep the highest-scored box.

In function detect_open_vocab it will first load the image where pil_image will crop the image and np_img is used for OCR functions. Then CLIP model encodes images and text; preprocess transforms a PIL crop to CLIP input tensor. Then it is tokenised and prompts are encoded and selective search is used to guess where objects might be in the image and then CLIP matches text meaning with image region and then similarity and dynamic threshold (Here dynamic threshold is set so that if an object has little bit low threshold but object is partially visible it should detect that also so by dynamic threshold , Score is set according to image.) is also computed and then regions are filtered . Then non_max_supression is applied on it



