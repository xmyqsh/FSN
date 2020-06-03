# FSN
Fully Sparse Network

Update:
两个epoch的结果，APH修好了：）用的是自己设计的新方法修好的~~~

OBJECT_TYPE_TYPE_VEHICLE_LEVEL_1: [mAP 0.54329] [mAPH 0.530153]

OBJECT_TYPE_TYPE_VEHICLE_LEVEL_2: [mAP 0.475108] [mAPH 0.463525]

OBJECT_TYPE_TYPE_PEDESTRIAN_LEVEL_1: [mAP 0.688584] [mAPH 0.566387]

OBJECT_TYPE_TYPE_PEDESTRIAN_LEVEL_2: [mAP 0.60111] [mAPH 0.493233]

OBJECT_TYPE_TYPE_SIGN_LEVEL_1: [mAP 0] [mAPH 0]

OBJECT_TYPE_TYPE_SIGN_LEVEL_2: [mAP 0] [mAPH 0]

OBJECT_TYPE_TYPE_CYCLIST_LEVEL_1: [mAP 0.167696] [mAPH 0.145285]

OBJECT_TYPE_TYPE_CYCLIST_LEVEL_2: [mAP 0.161117] [mAPH 0.139587]



FSN framework is natural for image semantic feature combining which could be provided by [CropNet](https://github.com/xmyqsh/CropNet) which is responsible for realtime 100m+ object detection as while as providing semantic feature for FSN.

[camera model PATENT](https://github.com/waymo-research/waymo-open-dataset/tree/master/third_party/camera) could be used in the realtime image semantic feature and Lidar Sparse feature combining.

Notice: FSN has not used RGB pixel or feature in the waymo open dataset leadboard result. 

FSN is inspired by StarNet and based on SECOND, spconv and use sparse resblock in Det3D, mmdetection framework, planning to write a tensorflow version mmdet framework for rapid experiments.
All of its computation power has been allocated on the points or voxels containing points.
It has good PEDESTRIAN AP as StarNet does. And it has smaller receptive field as StarNet does.

Dilation, ASPP, FPN could be adopted to enlarge the receptive field for better Vechile AP, with little computation effort by using spconv correctly.

6.5 FPS on Waymo Open Dataset with a coarse designed network.

Easy to learn, no more than 4 epoch for training

No ground plane detection, no class-wise balancing, no ensemble, one model result

No FPN, one scale feature detection

No history or futher data using, only using current frame.

In a word, just a innovate new feature has been used, no bells and whistles.





It is just a new, coarse, easy to learn framework.
Can be further optimize from speed to accuracy.



`APH` could be fixed in a new way.
All of the current good angle direction classification tools will hurt or slow down AP in FSN more or less.

What interesting is that the current result of FSN on the Challenge leadboard with a buggy angle direction classifier has the best AP of all with 4 epoch training time.

