# CV212-Zero-Shot-Object-Detection-Project
#By Raghav Bhargava (2023UCA1927) and Akshansh Kumar Gautam (2023UCA1881)
How code works
In function run_ocr it will first convert PIL image into an array for pytesseract and then it will get a dictonary with a list like top, width etc then it will loop with n boxes so that high confidence tokens can be appended and will be returned.

In function non_max_supression, it will remove overlapping duplicate detection boxes and will keep the highest-scored box.

In function detect_open_vocab, it will first load the image where pil_image will crop the image and np_img is used for OCR functions. Then CLIP model encodes images and text; preprocess transforms a PIL crop to CLIP input tensor. Then it is tokenised and prompts are encoded and selective search is used to guess where objects might be in the image and then CLIP matches text meaning with image region and then similarity and dynamic threshold (Here dynamic threshold is set so that if an object has little bit low threshold but object is partially visible it should detect that also so by dynamic threshold , Score is set according to image.) is also computed and then regions are filtere. Then non_max_supression is applied on it

Lastly in function demo(args) we give prompts where which object we want to detect from image , Then  we call detect_open_vocab to get image, detections, ocr_tokens . Then we use loop to do styling like extracting box, drawing rectangle boxes, compute text size, color mapping etc and saving OCR results. 

It all gets saved in result.jpeg

Summary

In this project me and my group have made zero shot object detection, where in the code we have libraries import cv2, NumPy, pytesseract, PIL, CLIP, torch.
I have used CLIP (Contrastive Language Image Pretrained) model where it starts with detecting areas of objects in an image and then for each region it detects similar patterns to get an image with respect to prompts and it checks with dynamic threshold values and after that it uses tesseract which acts as an OCR (Optical Character Recognition) tool that draws detection box and text box on output box (result).



