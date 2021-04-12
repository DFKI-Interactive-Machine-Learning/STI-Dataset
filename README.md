# DFKI's Search Target Inference Dataset
In our work on search target inference, we use two eye tracking datasets from visual search research. One by 
[Sattar et al.](https://www.mpi-inf.mpg.de/departments/computer-vision-and-machine-learning/research/gaze-based-human-computer-interaction/prediction-of-search-targets-from-fixations-in-open-world-settings/) 
which focusses on search target inference for media retrieval and one by 
[Koehler et al.](http://www.journalofvision.org/content/14/3/14.full)
which investigates top-down visual saliency in visual search.
We extended both datasets for being used with our approaches for inferring search targets of a visual search.
Each dataset is located in a separate folder. Per dataset we provide a `JSON`
file with all annotations and a folder that shall contain the corresponding raw images.
We do not provide the raw images on Github. **You can download a package with all images [here](https://iml.dfki.de/wp-content/uploads/2020/05/STI-Dataset.zip)**. 

The final folder structure should look as follows:
```
AmazonCovers/
  - images/
      - 1.jpg
      - ...
      - 100.jpg
  - Amazon.json
VIU/
  - images/
      - image_r_401.jpg
      - ...
      - image_r_800.jpg
  - VIU.json
README.md
```

### Amazon Book Cover Dataset by [Sattar et. al](https://www.mpi-inf.mpg.de/departments/computer-vision-and-machine-learning/research/gaze-based-human-computer-interaction/prediction-of-search-targets-from-fixations-in-open-world-settings/)

The Amazon Book Cover dataset consists of 100 image collages (`AmazonCovers/images`). 
For each collage, the dataset provides fixation data from six participants. 
We annotated the target object for each collage (i.e., 1/100 book covers) by a recangular bounding box and further described in an separate image file. The JSON tree for an image of the Amazon Book Cover dataset has the following structure:

* _image name_
    * __"fixations"__
        * __"1"__ : _list of [x, y] coordinates at fixations of user 1_
        * __"2"__ : _list of [x, y] coordinates at fixations of user 2_
        * ...
    * __"ground_truth"__
        * __"xmax"__: _maximal x coordinate of ground truth_
        * __"xmin"__: ...
        * __"ymax"__: ...
        * __"ymin"__: ...
    * __"size"__
        * __"height"__: _height of the search image_
        * __"width"__: _width of the search image_
    * __"target"__: _search target, i.e., the searched book cover_
    
If you use this part of the dataset, please cite the following publication:
```
@inproceedings{Stauden18,
  author    = {Sven Stauden and Michael Barz and Daniel Sonntag},
  editor    = {Frank Trollmann and Anni{-}Yasmin Turhan},
  title     = {Visual Search Target Inference Using Bag of Deep Visual Words},
  booktitle = {{KI} 2018: Advances in Artificial Intelligence - 41st German Conference 
              on AI, Berlin, Germany, September 24-28, 2018, Proceedings},
  series    = {Lecture Notes in Computer Science},
  volume    = {11117},
  pages     = {297--304},
  publisher = {Springer},
  year      = {2018},
  url       = {https://doi.org/10.1007/978-3-030-00111-7\_25},
  doi       = {10.1007/978-3-030-00111-7\_25}
}
```

### VIU Dataset by [Koehler et al.](https://labs.psych.ucsb.edu/eckstein/miguel/research_pages/saliencydata.html)
The VIU dataset was published in: Kathryn Koehler, Fei Guo, Sheng Zhang, Miguel P. Eckstein. 
[What Do Saliency Models Predict? [JoV 2014]](http://www.journalofvision.org/content/14/3/14.full)

The dataset provides fixation data from visual search trials of 19 participants for 397 images. 
We annotated each image with the ground truth region, i.e., the region that contains the search target of a particular trial. 
The annotation consists of at least one recangular bounding box. 
We also add the _cue word_ describing the target object for each image. 

The JSON tree for an image of the VIU dataset has the following structure:

* _image name_
    * __"cue"__ : _string describing the target object_
    * __"fixations"__
        * __"1"__ : _list of [x, y] coordinates at fixations of user 1_
        * __"2"__ : _list of [x, y] coordinates at fixations of user 2_
        * ...
    * __"ground_truth"__: [
        * __"xmax"__: _maximal x coordinate of one ground truth rectangle_
        * __"xmin"__: ...
        * __"ymax"__: ...
        * __"ymin"__: ...
        ...]
    * __"size"__
        * __"height"__: _height of the search image_
        * __"width"__: _width of the search image_
        
If you use this part of the dataset, please cite the following publication:
```
@inproceedings{Barz20,
  author = {Barz, Michael and Stauden, Sven and Sonntag, Daniel},
  title = {Visual Search Target Inference in Natural Interaction Settings with Machine Learning},
  year = {2020},
  isbn = {9781450371339},
  publisher = {Association for Computing Machinery},
  address = {New York, NY, USA},
  url = {https://doi.org/10.1145/3379155.3391314},
  doi = {10.1145/3379155.3391314},
  booktitle = {Symposium on Eye Tracking Research and Applications},
  articleno = {1},
  numpages = {8},
  keywords = {Search Target Inference, Machine Learning, Mobile Eyetracking, Visual Attention},
  location = {Stuttgart, Germany},
  series = {ETRA ’20}
}
```
