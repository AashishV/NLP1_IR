# NLP1_IR
NLP1 2017-18 UvA Project

Image Features link, https://aashishv.stackstorage.com/s/sEdlxbDqaPHeNxi

## Projects

Please find the project report requirements [here](https://github.com/tdeoskar/NLP1-2017/blob/master/project-reqs.md).


### Links
* [The Unreasonable Effectiveness of Recurrent Neural Networks](http://karpathy.github.io/2015/05/21/rnn-effectiveness/)
* [Understanding LSTM Networks](http://colah.github.io/posts/2015-08-Understanding-LSTMs/)
* [PyTorch Tutorials](https://github.com/yunjey/pytorch-tutorial)
* [PyTorch Data Loading Tutorial](http://pytorch.org/tutorials/beginner/data_loading_tutorial.html)

### Get Images
While for training your models you can handle the image features as a black box, for testing and anlysis you want to have a look at the actual image. The VQA dataset utilizes the 2014 version of [MSCOCO](http://cocodataset.org/). Many tasks like Image Captioning or Object Detection are using this dataset, so it might me worthwhile to download it. However, it is quite big (13GB train, 6GB validation, 6GB test). For this project you will only need the training dataset, since all datapoints are from this split. The image can be retrieved via the file name. The image id is equal the last digits of the image file name. 
Besides downloading the dataset, we are providing a second option. The MSCOCO annotations come with a flickr url where the images can be found online. The file `imgid2imginfo.json` contains the flickr url (and more image information) for the MSCOCO training and validation dataset. The file can be utilized as follows:

```python
import json

# load the image info file
with open('data/imgid2imginfo.json', 'r') as file:
    imgid2info = json.load(file)

print(imgid2info['265781'])
# RETURNS:
#{'coco_url': 'http://images.cocodataset.org/train2014/COCO_train2014_000000265781.jpg',
# 'date_captured': '2013-11-14 21:01:15',
# 'file_name': 'COCO_train2014_000000265781.jpg',
# 'flickr_url': 'http://farm6.staticflickr.com/5199/5882642496_9e58939526_z.jpg',
# 'height': 424,
# 'id': 265781,
# 'license': 1,
# 'width': 640}

