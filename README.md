# FSN
Fully Sparse Network

```
FSN is inspired by StarNet and based on SECOND, spconv and use sparse resblock in Det3D.
All of its computation power has been allocated on the points or voxels containing points.
It has good PEDESTRIAN AP as StarNet does. And it has smaller receptive field as StarNet does.

Dilation, ASPP, FPN could be adopted to enlarge the receptive field for better Vechile AP, with little computation effort by using spconv correctly.

6.5 FPS on Waymo Open Dataset with a coarse designed network.

Easy to learn, no more than 4 epoch for training

No ground plane detection, no class-wise balancing, no ensemble, one model result

No FPN, one scale feature detection

No history or futher data using, only using current frame.

In a word, just a innovate new feature has been used, no bells and whistles.

```


```
It is just a new, coarse, easy to learn framework.
Can be further optimize from speed to accuracy.

```

```
`APH` could be fixed in a new way.
All of the current good angle direction classification tools will hurt or slow down AP in FSN more or less.

What interesting is that the current result of FSN on the Challenge leadboard with a buggy angle direction classifier has the best AP of all with 4 epoch training time.
```
