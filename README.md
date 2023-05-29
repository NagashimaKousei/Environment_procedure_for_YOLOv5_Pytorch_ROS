# Environment_procedure_for_YOLOv5_Pytorch_ROS
A repository representing the environment instructions for YOLOv5_Pytorch_ROS
# YOLOv5v4.0を構築する際につまずいたこと
- tagの指定方法
- train.py時のエラー
# tagの指定方法
以下を参考にtagの指定を行った

https://qiita.com/colorrabbit/items/e608d5a159e628f297b0

注意点として、タグをしてしながらgit cloneしない
```
git clone git@github.com:ultralytics/yolov5.git
```

# train.py時のエラー
以下のサイトの手順に従う
https://discuss.roboflow.com/t/error-roboflow-custom-scaled-yolov4/1920/2

主にloss.pyが原因

