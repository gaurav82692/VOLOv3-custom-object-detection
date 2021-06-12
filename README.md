# VOLOv3-custom-object-detection
1. Download Dataset
2. Annotate in xml format
3. Convert xml to txt ---->   https://github.com/Isabek/XmlToTxt
4. Clone Darknet repo ----> https://github.com/AlexeyAB/darknet
5. Create a folder "obj" darknet ->data-> obj ->(image +annotations)
6. download pre-trained weight  ----> https://pjreddie.com/media/files/darknet53.conv.74
7. put weights in darknet folder
8. Open cfg folder
9. Make a copy of yolov3 file and remane it as yolov3-custom.cfg
10. Open yolov3-custom.cfg file<br>
	10.1 comment(testing--->batch,subdivision)<br>
	10.2 uncomment(training--->batch,subdivision)<br>
	10.3 if cuda error found change GPU sub division = 23 or 64<br>
	10.4 max_batches = no of classes*2000<br>
	10.5 Step = 80% of max_batches , 90% of max_batches<br>
	10.6 Search fo yolo ---> change classes<br>
	10.7 filters = (classes+5)*3 do it fo every yolo layer<br>
	10.8 random=1<br>
11. go to data folder
	11.1 create obj.names<br>
	11.2 put all the name of classes in obj.names<br>
	11.3 create obj.data<br>
		classes = 6<br>
		train = data/train.txt<br>
		valid = data/test.txt<br>
		names = data/obj.names<br>
		backup = backup/<br>

12. generate train.txt and test.txt  through code   https://github.com/hmgtech/Requirents-For-Darknet/blob/master/generate_train.py   (so that same of annotations images wiil be saved in txt format)
  
