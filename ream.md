1. Download Dataset
2. Annotate in xml format
3. Convert xml to txt ---->   https://github.com/Isabek/XmlToTxt
4. Clone Darknet repo ----> https://github.com/AlexeyAB/darknet
5. Create a folder "obj" darknet ->data-> obj ->(image +annotations)
6. download pre-trained weight  ----> https://pjreddie.com/media/files/darknet53.conv.74
7. put weights in darknet folder
8. Open cfg folder
9. Make a copy of yolov3 file and remane it as yolov3-custom.cfg
10. Open yolov3-custom.cfg file
	10.1 comment(testing--->batch,subdivision)
	10.2 uncomment(training--->batch,subdivision)
	10.3 if cuda error found change GPU sub division = 23 or 64
	10.4 max_batches = no of classes*2000
	10.5 Step = 80% of max_batches , 90% of max_batches
	10.6 Search fo yolo ---> change classes
	10.7 filters = (classes+5)*3 do it fo every yolo layer
	10.8 random=1
11. go to data folder
	11.1 create obj.names
	11.2 put all the name of classes in obj.names
	11.3 create obj.data
		classes = 6
		train = data/train.txt
		valid = data/test.txt
		names = data/obj.names
		backup = backup/

12. generate train.txt and test.txt  through code   https://github.com/hmgtech/Requirents-For-Darknet/blob/master/generate_train.py   (so that same of annotations images wiil be saved in txt format)
  
