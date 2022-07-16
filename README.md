# You-Only-Look-Once-YOLO-model
YOLOv3 in using cv2.dnn.readNetFrom()
WE use a pre-trained YOLOV3 Model and use OpenCV to run inferences over a few images

Steps Invovled-

*Use Pretrained YOLOV3 weights (237MB)- https://pjreddie.com/media/files/yolov3.weights
*Create our blob object which is our loaded model
*Set the backend that runs the model

The input to the network is a called blob object.

The function cv.dnn.blobFromImage(img, scale, size, mean) transforms the image into a blob:
blob = cv.dnn.blobFromImage(img, 1/255.0, (416, 416), swapRB=True, crop=False)

It has the following parameters:

*the image to transform
*the scale factor (1/255 to scale the pixel values to [0..1])
*the size, here a 416x416 square image
*the mean value (default=0)
*the option swapBR=True (since OpenCV uses BGR)

Note A blob is a 4D numpy array object (images, channels, width, height). The image below shows the red channel of the blob. You notice the brightness of the red jacket in the background.

NOTE: How to Perform non maximum suppression given boxes and corresponding scores.
indices  =   cv.dnn.NMSBoxes(    bboxes, scores, score_threshold, nms_threshold[, eta[, top_k]]

Parameters-

*bboxes a set of bounding boxes to apply NMS.
*scores a set of corresponding confidences.
*score_threshold a threshold used to filter boxes by score.
*nms_threshold a threshold used in non maximum suppression. indices the kept indices of bboxes after NMS.
*eta a coefficient in adaptive threshold formula: nms_thresholdi+1=eta⋅nms_thresholdi.
*top_k if >0, keep at most top_k picked indices.
