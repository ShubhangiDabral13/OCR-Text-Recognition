
# OCR Text recognition with Python and API

## Table of Content:
* [Overiew](https://github.com/ShubhangiDabral13/OCR-Text-Recognition/OCR-Text-recognition-with-Python-and-API#Overview)
* [Libraries and Modules required](https://github.com/ShubhangiDabral13/OCR-Text-Recognition/OCR-Text-recognition-with-Python-and-API#Steps-for-Implementation#Libraries-and-Modules-required)
* [Steps for Implementation](https://github.com/ShubhangiDabral13/OCR-Text-Recognition/edit/master/OCR%20Text%20recognition%20with%20Python%20and%20API#Steps-for-Implementation)


## Overview

In this project i have worked on how to recognize the text from a picture using Python and orc.space API. OCR (Optical character recognition) is the process by which the computer recognizes the text from an image.ocr.space is an OCR engine that offers free API.

## Libraries and Modules required

* **cv2:** it is use to read image
* **numpy:** it is library used for mathematical computation.  
* **request:** to make request to the api
* **io:** Converting image to byte
* **json:** Converting string into json

 ## Steps for Implementation
 
 ### 1) Import the libraries and load the image
 
Import all the libraries that we need (Opencv, IO, numpy, requests, json).IO and Json are by default already installed on python, need to  install the other libraries.

     To import requests:
        pip install requests
        
 **The image we are reading is :**
 
![screenshot-300x169](https://user-images.githubusercontent.com/44902363/85969873-8698d100-b9e6-11ea-88b9-1450c90ae065.jpg)

 As we need to focus only on the text so we will crop the image and remove extra spaces
 
 **After cropping the image:**
 
 
![roi-300x213](https://user-images.githubusercontent.com/44902363/85969821-610bc780-b9e6-11ea-898c-1fed5cf91801.jpg)


### 2).Set the OCR engine

We now have the image and our goal is to send the image to the orc.space server in order to be processed. 

* Before sending the image to the server we need to compress it. The simple reason for this compression is that using the free service we can send image with maximum 1mb of size, so this compression will shrink the size of our image.

        _, compressedimage = cv2.imencode(".jpg", roi, [1, 90])
        
 * We will also convert image to bytes.
 
       file_bytes = io.BytesIO(compressedimage)
       
       
Later we send the bytes to the server using the python library requests.
We need to pass three parameters:

   1).the first is the url_api
   
   2).Called “Files” which contains the name of the file and the file bytes we generated before after we compressed the image.
   
   3).And then “Data” which contains the post parameters of the OCR engine.
   
We need to insert the api key where now it’s written “xxxxxxxxxxxx”, and language is the language of our text. By default is english.

         result = requests.post(url_api,
              files = {"screenshot.jpg": file_bytes},
              data = {"apikey": "XXXXXXXXX",
                      "language": "eng"})
                      
                      
### 3).Read the Result

The result from the server is a string.
We’re going first of all to extract the content of result, then we convert the content into a dictionary.
Extract the result from the dictonary and display it.


### Author

#### Shubhangi Dabral (ShubhangiDabral13)
<a href="https://twitter.com/Shubhi_Dabral"><img 
src="https://news.wjct.org/sites/wjct/files/styles/medium/public/201407/v65oai7fxn47qv9nectx.png" align="left" height="50" width="50" ></a>
<a href="https://www.linkedin.com/in/shubhangi-dabral-b79705145/"><img src="https://cdn2.iconfinder.com/data/icons/simple-social-media-shadow/512/14-512.png" align="left" height="60" width="60" ></a>




