# slowfast_implementation
This repository provides an example on how to prepare data in AVA format and do the training for the SlowFast model. 

- The official repo of SlowFast is from [https://github.com/facebookresearch/SlowFast](https://github.com/facebookresearch/SlowFast) . Some modifications have made to its setting in order to run the model for customized videos. All the relevant files including the modifications and the models have been put in the `SlowFast` directory. 

- A requirements list (for your reference) has been made for building the enviornment for training or doing inference for the SlowFast model. It can be found in the `reference_modules.txt` 

- Main codes on how to prepare training data is put in the `test_data_prep` directory.

- There is supposed to be a pretrained SlowFast model in `SLOWFAST_32x2_R101_50_50.pkl` inside `test_data_prep/test_data_run`. It can be downloaded from [here](https://drive.google.com/file/d/1MjFVfZq4opyHDQpRAs3w3Aak8t_UDqwm/view?usp=sharing).

In the `test_data_prep` directory, if you want to annotate the detection and motion by hand, `CutVideosI.ipynb` and `CutVideosII.ipynb` show how to cut a video into 1 frame/second (for annotating detection box) and 30 frames/second (for annotating action) respecively. But they are for demonstration only, I did not use them to do the annotations for the training code. Instead, I took data from [Edinburgh Pig Behavior Video Dataset](https://homepages.inf.ed.ac.uk/rbf/PIGDATA/) (exmaple videos, which can be obatined from (1)[here](https://drive.google.com/file/d/1WjrD2Mb5pkEsKPnswCw2Hh50yvdb2vmn/view?usp=sharing) and (2)[here](https://drive.google.com/file/d/1et4a6anXRdICe6unYUSKS5gsLi5vP-g_/view?usp=sharing) , and annotations organized in `test_data_prep/test_video directory`) and use the preannotated info in the `behvaiour_15.npy` file for each video. The most important file to prepare data from the video and annotations is the `test_data_prep/create_slowfast_data_AVA.ipynb` . The code to do the training is in `test_data_run/train_PIGS.ipynb` . The highlighted files mentioned are highlighted below:
```
├── SlowFast # SlowFast models with modifications made for customized videos
├── reference_modules.txt # module requirement list for reference
├── test_data_prep
│   ├── CutVideosI.ipynb # cut a video into 1 frame/second (demo only, results not used)
│   ├── CutVideosII.ipynb # cut a video into 30 frames/second (demo only, results not used)
│   ├── test_video # example videos with annotation files
│       ├── 2019-11-11--11_34_50_000000 # can downloaded from https://drive.google.com/file/d/1WjrD2Mb5pkEsKPnswCw2Hh50yvdb2vmn/view?usp=sharing
│       └── PIGS021219a_000545.mp4 # can downloaded from https://drive.google.com/file/d/1et4a6anXRdICe6unYUSKS5gsLi5vP-g_/view?usp=sharing
│   ├── create_slowfast_data_AVA.ipynb # MAIN code to prepare the relevant data in AVA format
│   └── test_data_run
│       ├── SLOWFAST_32x2_R101_50_50.pkl # pretrained model weights, can be downloaded from https://drive.google.com/file/d/1MjFVfZq4opyHDQpRAs3w3Aak8t_UDqwm/view?usp=sharing
│       └── train_PIGS.ipynb # MAIN code to do the SlowFast model training
```


