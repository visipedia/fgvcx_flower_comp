![Banner](https://rawgit.com/richardaecn/fgvcx_flower_comp/master/assets/flower_cover.png)

# 2018 FGVCx Flower Classification Challenge
The 2018 competition is part of the [FGVC^5 workshop](https://sites.google.com/view/fgvc5/home) at [CVPR](http://cvpr2018.thecvf.com/).
Our sponsor, the [Xingse App](https://www.xingseapp.com/) & [PictureThis App](https://www.picturethisai.com/), has provided a dataset from a carefully curated database containing over 650,000 flower images from 997 flower species.

Please open an issue if you have questions or problems with the dataset.

## Kaggle
We are using Kaggle to host the leaderboard. Checkout the competition page [here](https://www.kaggle.com/c/flower-challenge-fgvc-2018).

## Dates
|||
|------|---------------|
Data Released|April 25, 2018|
Submission Deadline|June 15, 2018|
Winners Announced|June 22, 2018|

## Details
There are a total of 997 flower species in the dataset, with 650,000 training images and 4,985 validation images. The testing set contains 7,976 images.

## Evaluation
We use top-1 classification accuracy as the evaluation metric. For each image <img src="https://rawgit.com/richardaecn/fgvcx_flower_comp/master/svgs/77a3b857d53fb44e33b53e4c8b68351a.svg?invert_in_darkmode" align=middle width=5.642109pt height=21.60213pt/>, an algorithm will produce 1 label <img src="https://rawgit.com/richardaecn/fgvcx_flower_comp/master/svgs/bb29cf3d0decad4c2df62b08fbcb2d23.svg?invert_in_darkmode" align=middle width=9.52017pt height=22.74591pt/>. For this competition each image has one ground truth label <img src="https://rawgit.com/richardaecn/fgvcx_flower_comp/master/svgs/681a37b53b66acbc455e39ca3e6f1c41.svg?invert_in_darkmode" align=middle width=12.444795pt height=14.10255pt/>, and the error for that image is:
<p align="center"><img src="https://rawgit.com/richardaecn/fgvcx_flower_comp/master/svgs/d89b544c1c8649aab60422b5cf483052.svg?invert_in_darkmode" align=middle width=117.29916pt height=24.865665pt/></p>
Where
<p align="center"><img src="https://rawgit.com/richardaecn/fgvcx_flower_comp/master/svgs/7a45c501d5042bd031a267f008fa2ae6.svg?invert_in_darkmode" align=middle width=190.2021pt height=49.13139pt/></p>

The overall error score for an algorithm is the average error over all <img src="https://rawgit.com/richardaecn/fgvcx_flower_comp/master/svgs/f9c4988898e7f532b9f826a75014ed3c.svg?invert_in_darkmode" align=middle width=14.94405pt height=22.38192pt/> test images:
<p align="center"><img src="https://rawgit.com/richardaecn/fgvcx_flower_comp/master/svgs/444adcac0c7cbb4a8419ee1484625349.svg?invert_in_darkmode" align=middle width=118.05123pt height=41.069655pt/></p>

## Guidelines
Participants are restricted to train their algorithms on the 2018 FGVCx Flower Classification competition train and validation sets. Pretrained models may be used to construct the algorithms (e.g. ImageNet pretrained models) as long as participants do not actively collect additional data for the target species in the 2018 FGVCx Flower Classification competition. Please specify any and all external data used for training when uploading results.

The general rule is that we want participants to use only the provided training and validation images to train a model to classify the test images. We do not want participants crawling the web in search of additional data for the target categories. Participants should be in the mindset that this is the only data available for those categories.

Participants are allowed to collect additional annotations (e.g. bounding boxes) on the provided training and validation sets. Teams should specify that they collected additional annotations when submitting results.

## Annotation Format
We closely follow the annotation format of the [COCO dataset](http://mscoco.org/dataset/#download).
For possibly better identification of flower species, extra infomation are provided:
1. We provide when and where the images were uploaded. Note that those infomation are only available on ~60% of images.
2. We provide taxonomic information including "Family" and "Genus" for all flower species.
3. We provide extra 200,000 unlabeled images.

The annotations are stored in the [JSON format](http://www.json.org/) and are organized as follows:
```
{
  "info" : info,
  "images" : [image],
  "categories" : [category],
  "annotations" : [annotation],
  "licenses" : [license]
}

info{
  "year" : int,
  "version" : str,
  "description" : str,
  "contributor" : str,
  "url" : str,
  "date_created" : datetime,
}

image{
  "id" : int,
  "width" : int,
  "height" : int,
  "file_name" : str,
  "license" : int,
  "rights_holder" : str
  "upload_latitue": float
  "upload_longitude": float
  "upload_date": str
}

category{
  "id" : int,
  "genus": str
  "family": str
  "name" : str,
}

annotation{
  "id" : int,
  "image_id" : int,
  "category_id" : int
}

license{
  "id" : int,
  "name" : str,
  "url" : str
}
```

## Submission Format
The submission format for the Kaggle competition is a csv file with the following format:
```
id,predicted
12345, 23
67890, 42
```
The `id` column corresponds to the test image id. The `predicted` column corresponds to 1 predicted category id. You should have one row for each test image.

## Terms of Use
By downloading this dataset you agree to the following terms:

1. You will abide by the [Xingse & PictureThis User Agreement (EULA)](https://www.picturethisai.com/static/user_agreement)
2. You will use the data only for non-commercial research and educational purposes.
3. You will NOT distribute the above images.
4. Xingse & PictureThis makes no representations or warranties regarding the data, including but not limited to warranties of non-infringement or fitness for a particular purpose.
5. You accept full responsibility for your use of the data and shall defend and indemnify Xingse & PictureThis, including its employees, officers and agents, against any and all claims arising from your use of the data, including but not limited to your use of any copies of copyrighted images that you may create from the data.


## Data
(TBD) 

Download the dataset files here:
