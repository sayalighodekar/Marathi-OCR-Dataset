# Marathi-OCR-Dataset
A collection of about 12k Marathi word images with corresponding labels, useful for Devanagari Optical Character Recognition.

# Description
There is a lack of publicly available datasets at word/line level for Devanagari character recognition. We created this dataset containing Marathi vocabulary of ~12k word images and thier corresponding text labels encoded in utf-8 format. Words are segmented from  Marathi books in PDF and .epub format, available at http://www.esahity.com/ . We used 12 books from different genres to include diversity in vocabulary and font variation. It also removed the dependancy on domain specific words and redundant Marathi numerals. The dataset is based on [IAM Handwriting Dataset](http://www.fki.inf.unibe.ch/databases/iam-handwriting-database)

We created this dataset using [pytesseract](https://pypi.org/project/pytesseract/) which is a wrapper for Google Tesseract-OCR engine. The challenge with using Tesseract-OCR for Indic languages is that it is trained using the same approach as European languages. It fails to recognize compund words (common in Devanagari script) which are consonant-vowel sequences represented as single a unit. Devanagari script also contains various diacritics written with the characters. To eliminate these errors and inconsistencies in the predicted output, we manually correct the text labels. The images are resized into a fixed format of 300x50 pixels and stored in JPEG format with a resolution of 96 dpi horizontally and vertically, so that they can be fed directly to neural nets. The length of words varies from 2 characters upto as long as 15-20 characters. We also apply pre-processing techniques like binarization and image thresholding  using OpenCV and PIL, for cleaner images.  <br />

# Usage
The file `images.zip ` contains the Marathi words images and `labels.txt` contains the corresponding text. 
This dataset can be leveraged to improve the existing OCR systems, see [Train Tesseract 4.0](https://tesseract-ocr.github.io/tessdoc/TrainingTesseract-4.00). More widely, it can be used to train hybrid CNN-LSTM models from scratch, see [Text Recognition System using TensorFlow](https://towardsdatascience.com/build-a-handwritten-text-recognition-system-using-tensorflow-2326a3487cd5). 
 
