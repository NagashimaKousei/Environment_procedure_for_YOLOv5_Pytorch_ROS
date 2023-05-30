# Environment_procedure_for_YOLOv5_Pytorch_ROS
A repository representing the environment instructions for YOLOv5_Pytorch_ROS
# YOLOv5v4.0を構築する際につまずいたこと
- tagの指定方法
- train.py時のエラー
- Upsample' object has no attribute 'recompute_scale_factor
# tagの指定方法
以下を参考にtagの指定を行った

https://qiita.com/colorrabbit/items/e608d5a159e628f297b0

注意点として、タグを指定しながらgit cloneしない
```
git clone git@github.com:ultralytics/yolov5.git
```

# train.py時のエラー
以下のサイトの手順に従う
https://discuss.roboflow.com/t/error-roboflow-custom-scaled-yolov4/1920/2

主にloss.pyが原因

# Upsample' object has no attribute 'recompute_scale_factor
upsampling.pyの155行目からを変更を行う必要がある



# YOLOv5_Pytorch_ROSの実行手順
ステップ１
```
roslaunch yolov5_pytorch_ros detector.launch
```

この際に、重みのパスをしっかり指定する

ステップ2 カメラのノードを指定する
```
rosrun usb_cam usb_cam_node _video_device:=/dev/video0
```

ステップ3
```
rviz
```
起動後、AddのBytopicでimage(camera)を指定する

