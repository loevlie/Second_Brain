
### Reduce the size of a video 

```
 ffmpeg -i input.mp4 -vcodec libx265 -crf 28 output.mp4
```


### Finding the unique RGB values in a numpy array (useful for working with semantic segmentation masks):

```python
np.unique(img.reshape(-1, img.shape[2]), axis=0)
```

