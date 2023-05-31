# A repository to prepare for launching YOLOv5_Pytorch_ROS
A repository representing the environment instructions for YOLOv5_Pytorch_ROS
# YOLOv5v4.0の環境
https://github.com/ultralytics/yolov5/tree/v4.0
# YOLOv5v4.0を構築する際につまずいたこと
- tagの指定方法
- train.py時のエラー
- Upsample' object has no attribute 'recompute_scale_factor(人によっては不要)
# tagの指定方法
以下を参考にtagの指定を行った

https://qiita.com/colorrabbit/items/e608d5a159e628f297b0

注意点として、タグを指定しながらgit cloneしない

スケールでのエラーが出る可能性がある
```
git clone git@github.com:ultralytics/yolov5.git
```

# train.py時のエラー
以下のサイトの手順に従う

https://discuss.roboflow.com/t/error-roboflow-custom-scaled-yolov4/1920/2

主にloss.pyが原因

# Upsample' object has no attribute 'recompute_scale_factor
upsampling.pyの155行目からを変更を行う必要がある

以下のリンクを参考にプログラムの変更を行った

https://miyashinblog.com/yolov5/



# YOLOv5_Pytorch_ROSの実行手順
ステップ1

以下のリポジトリからyolov5_pytorch_rosの環境構築を行う

https://github.com/open-rdc/yolov5_pytorch_ros/tree/detect_landmark

ステップ2
```
roslaunch yolov5_pytorch_ros detector.launch
```

この際に、重みのパスを指定する

ステップ3 カメラのノードを指定する
```
rosrun usb_cam usb_cam_node _video_device:=/dev/video0
```

ステップ4
```
rviz
```
起動後、AddのBytopicでimage(camera)を指定する

