
# Text recognition (OCR) with Tesseract and Opencv

## Table of Content:
* [Overview](https://github.com/ShubhangiDabral13/OCR-Text-Recognition/edit/master/Text%20recognition%20(OCR)%20with%20Tesseract%20and%20Opencv#Overview)
* [Libraries and Modules required](https://github.com/ShubhangiDabral13/OCR-Text-Recognition/edit/master/Text%20recognition%20(OCR)%20with%20Tesseract%20and%20Opencv#Libraries-and-Modules-required)
* [Installation Of Modules](https://github.com/ShubhangiDabral13/OCR-Text-Recognition/edit/master/Text%20recognition%20(OCR)%20with%20Tesseract%20and%20Opencv#Installation-of-Modules)
* [Steps for Implementation](https://github.com/ShubhangiDabral13/OCR-Text-Recognition/edit/master/Text%20recognition%20(OCR)%20with%20Tesseract%20and%20Opencv#Steps-for-Implementation)
* [Inspiration](https://github.com/ShubhangiDabral13/OCR-Text-Recognition/edit/master/Text%20recognition%20(OCR)%20with%20Tesseract%20and%20Opencv#Inspiration)



## Overview 

In this project i have worked on how to recognize the text from a picture using Tesseract.

Python-tesseract is an optical character recognition (OCR) tool for python. That is, it will recognize and “read” the text embedded in images. Python-tesseract is a wrapper for Google's Tesseract-OCR Engine. It is open source and it is developed by google since 2006.


## Libraries and Modules required

* **cv2:** we will use the python programming language and Opencv to load the image, and do some image preprocessing (for example remove the areas where there is no text, remove some noise, apply some image filter to make the text more readable).
* **numpy:** it is library used for mathematical computation.  
* **Tesseract:** it’s the OCR engine, so the core of the actual text recognition. It takes the image and in return gives us the text.
* **Pytesseract:** it’s the tesseract binding for python. With this library we can use the tesseract engine with python with just a few lines of code.

## Installation of Modules

### 1). Installing Tesseract

* **Windows:**
  If you have windows, go on this page https://github.com/UB-Mannheim/tesseract/wiki, download and install tesseract 64 bit.

* **Linux**
On Linux you can simply open the terminal and insert the following commands:

     sudo apt install tesseract-ocr
     sudo apt install libtesseract-dev
     

* **Mac**
To install tesseract on Mac use this command:

     sudo port install tesseract


If the commands don’t work, you can refer to the Tesseract website page for more instructions: https://tesseract-ocr.github.io/tessdoc/Home.html.


### 2).Installing PyTesseract

Pytesseract is an essential library if we want to use tesseract with Python. It can be easily installed as any other python library using the pip command.
So copy the following commands on your terminal.

    pip install pytesseract
    pip3 install pytesseract


## Steps for Implementation

### 2).Read text from an image

The picture that i will use in first section is 

![bigsleep](https://user-images.githubusercontent.com/44902363/85974720-e9dd3000-b9f3-11ea-8257-949f40231b6e.jpg)

After importing the modules and loading the image to extract the text using Pytesseract we get the output as

            THE BIG SLEEP
            by Raymond Chandler

            It was about eleven o'clock in the morning, mid October, with the sun not
            shining and a look of hard wet rain in the clearness of the foothills. I was
            wearing my powder-blue suit, with dark blue shirt, tie and display
            handkerchief, black brogues, black wool socks with dark blue clocks on
            them. I was neat, clean, shaved and sober, and I didn’t care who knew it. I
            was everything the well-dressed private detective ought to be. T was
            calling on four million dollars.
            ‘The main hallway of the Sternwood place was two stories high. Over the
            entrance doors, which would have let in a troop of Indian elephants, there
            ‘was a broad stained-glass panel showing a knight in dark armor rescuing


~ As we have given the clear picture so the text is being diplayed in the correct and appropriate way.
What if we have not that perfect picture. For that we need to tune tesseract and also need to preprocess the image.

### 3).Tune tesseract to improve the text recognition

In the section 2 we have seen how easy it is to run Tesseract using python, and the result was really good as the engine performed really well and the text recognition was almost perfect.

Now we’re going to make the text recognition more challenging, giving Tesseract a picture (instead of a scanning a book page), where the orientation of the text is not exactly horizontal but there is a slope, where the lightening changes on different part of the page and where there are elements that are not text and should not be there.

This is the image we’re going to test.

![book_page](https://user-images.githubusercontent.com/44902363/85975295-5278dc80-b9f5-11ea-954e-7261fdb9d751.jpg)

So for this image we will do "Image preproccesing". These are operations that we’re going to make before trying to detect the text, by improving the image as much as possible to make the text more clear.

There are a lot of operations we can do to improve the image before giving it to the OCR. Here below I’m just going to give you a few ideas.

* **Convert image to grayscale:** we only need the text, we don’t care about colors. The text is simpler to identify on a grayscale image.

* **Change the size of the image:** we can use as maximum resolution, the one where the text is clear for to read for our eyes.

* **Removing noise:** what to us look like a clear text, if we zoom it the image, pixel by pixel, might not be that clear but there might be some noise. So we can for example blur the image.

* **Convert image to black and white:** by converting the image to black and white, we set tha background as all white, and the text black. In this way we solve the problem to recognize the text when lightening changes constantly on the picture.

And that’s how the image looks like after the preprocessing operations:

![Screenshot (211)](https://user-images.githubusercontent.com/44902363/85975630-39bcf680-b9f6-11ea-89f1-4ba8352a23b2.png)

As you see after the preprocessing, the text is much easier to read, and that makes a huge difference for the OCR engine.

The final output that we get is

Design before you implement

                        scularly if the project involves designing a product or service, ensure
                        Pare e the best possible answer in the design phase before you start
                        u hav tation. Another 80/20 rule says that 20 per cent of the prob-
                        imple any design project cause 80 per cent of the costs or overruns;
                        Jems W g0 per cent of these critical problems arise in the design phase
                        and ae expensive to correct later, requiring massive rework and
                        and are

                        . gome cases retooling.
                        in


## Inspiration

* [What is tesseract and how it works?](https://medium.com/@Bytepace/what-is-tesseract-and-how-it-works-dfff720f4a32) By BytePace

* [How does Tesseract-OCR work with Python?](https://medium.com/@latifvardar/how-does-tesseract-ocr-work-with-python-a6bccf85a002) By latif vardar


### Author

#### Shubhangi Dabral (ShubhangiDabral13)
<a href="https://twitter.com/Shubhi_Dabral"><img 
src="https://news.wjct.org/sites/wjct/files/styles/medium/public/201407/v65oai7fxn47qv9nectx.png" align="left" height="50" width="50" ></a>
<a href="https://www.linkedin.com/in/shubhangi-dabral-b79705145/"><img src="https://cdn2.iconfinder.com/data/icons/simple-social-media-shadow/512/14-512.png" align="left" height="60" width="60" ></a>


 





