# Welcome to *Smart Shopping Cart*
 
This repo describes the main idea of the project and  how to setup the Smart Shopping Cart prototype in your machine.
*Here we go*.

# Main Idea
The idea is to build an autonomous shopping cart with and intent to eradicate the problem of waiting in long queues at the billing counter. The items present inside the cart will be accurately detected and accordingly an invoice will be generated and different payment options will be provided.


## Brief description of how *Smart Shopping Cart* works
The user is required to scan the barcode using the barcode scanner present on the cart. There-after the data (such as weight, price) can be fetched from the primary server of the store using the integrated WI-FI module of the cart. The floor of the cart is replaced by a sophisticated weighing machine which will ensure that the total increase in the weight of the cart is equal to the weight of the current item which is being placed inside the cart by the user. The primary camera installed on the brim of the cart will act as the second line of defense again theft. The camera is capable of capturing live images of items currently being placed in the cart. These images will then be processed using computer vision to obtain the category and name of the product which will be crosschecked with the details fetched using the barcode. In case of any mismatch in weight or details error message will be displayed on the screen. If both of the security checks are passed then only the item will be added to the list of currently present items in the cart. Brief Description: The user need to scan the barcode of the item using the barcode scanner present on the shopping cart. The number fetched by the barcode reader will be used to retrieve product information from the main server of the store using the integrated WIFI module of the shopping cart .After successful completion of this step the user is expected to put down the scanned item inside the cart. The floor of the cart is actually a USB electronic scale which is capable of measuring the weight of the items present inside the cart at an instance. Once the item is placed by the user the computer application will fetch the current reading of the scale and total increase in weight of the cart will be calculated by calculating the difference of the weight of the cart before and after placing the item. This increase in weight will be matched with the fetched weight of the incoming product. In case of any mismatch an error message will be displayed on the screen. A camera is also installed on the brim/top edge of the cart which is capable of taking continues images of the items which are being placed by the user these images will then be fed to a convolution neural network which was already been trained on the images of the product present in the stores. The network will output the product category and product related information of the input image. This obtained information will be matched with the information fetched using the barcode. These two security measures will ensure that the item which was scanned by the user is actually the item which is being placed inside the cart by matching the weight and product information obtained using computer vision. Once both of the security checks are passed the product is added to the list of items present inside the cart. If the user wants to remove an item from the cart then he/she can do so by pressing a button place alongside the barcode scanner that will indicate the software application to remove the scanned object from the list(if present). Once the customer is done shopping an invoice of the list of items will be generated and will be displayed on the screen then user can choose to pay the amount using any of the available mode of payments.

**DUH!!** Enough of words, lets move to the coding part.

# Setup of Object detection model for Cart
We can divide this part in the following parts:
- Setting up enviroment.
 - Installing the dependencies.
 - Finally, launching the application by running the output scripts.

## Setting up enviroment
A PYTHONPATH variable must be created that points to the \models, \models\research, and \models\research\slim directories. Do this by issuing the following commands (from any directory):

    C:\> set PYTHONPATH=C:\shopping_cart\models;C:\shopping_cart\models\research;C:\shopping_cart\models\research\slim
    C:\> set PATH=%PATH%;PYTHONPATH




## Installing the dependencies
Install the latest version of Anaconda and then install the following modules using `conda install or pip install`.

    C:\> conda install -c anaconda protobuf
    C:\> pip install pillow
    C:\> pip install lxml
    C:\> pip install Cython
    C:\> pip install contextlib2
	C:\> pip install jupyter
	C:\> pip install matplotlib
	C:\> pip install pandas
	C:\> pip install opencv-python


## Launching the application

Navigate to the /models/research/object_detection in terminal.
Now run the following command

    C:\> python Object_detection_webcam.py 

# Sample outputs
![
](https://lh3.googleusercontent.com/-zBChqJkeqAfR3prj0FcvDlb7j9nXL_o1eF8qGXckoR9E9I7mvJbFb-7njz11hn1SycR-kwkK5ni "face wash")
![enter image description here](https://lh3.googleusercontent.com/1zAJ6l_Er_1Nn18FwG4fLx6cOm5ogcwFDSuqVBcK8CgR7_22xp8QRcSLnFw1MyXbdafI6Gd-RlC1 "3 Classes")
![enter image description here](https://lh3.googleusercontent.com/5aLurDZQGFKLtGdsp-dXqcIOoaqfHmRoL1EH2mbHrY_UiRq8XEfwk-7qSoApIeTtAJr19NM9u7VG "Multiple objects")




