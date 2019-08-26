# mxnet_google_tpu

Python Scripts using Google's Corel TPU for robotic real-time object recognition then upload to AWS S3 bucket storage and further processing.

The script performs the following actions - dependant upon the parameters that are passed to it:

1) Read in TFLite Model and initialise USB TPU
2) OpenCV - Open camera
3) Generate bounded box video with identified objects (If running from console this is obviously ignored)
4) Save image to video stream
5) Keep track of identified objects (later save this meta data into json formatted file)
6) If no objects are detected for a confgiurable amount fo time (default 120 sec) then close down process
7) Upon shutting down if objects have been detected upload video and meta data to specified AWS S3 location for storage and further processing if req.
