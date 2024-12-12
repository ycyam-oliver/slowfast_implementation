# slowfast_implementation
This repository provides an example on how to prepare data in AVA format and do the training for the SlowFast model. 

- The official repo of SlowFast is from https://github.com/facebookresearch/SlowFast . Some modifications have made to its setting in order to run the model for customized videos. All the relevant files including the modifications and the models have been put in the SlowFast model. 

- A requirements list (for your reference) has been made for building the enviornment for training or doing inference for the SlowFast model. It can be found in the reference_modules.txt 

- Main codes on how to prepare training data is put in the `test_data_prep` directory. In the directory, if you want to annotate the detection and motion by hand, `CutVideosI.ipynb` and `CutVideosII.ipynb` show how to cut a video into 1 frame/second (for annotating detection box) and 30 frames/second (for annotating action) respecively. But they are for demonstration only, I did not use them to do the annotations for the training code. Instead, I took data from https://homepages.inf.ed.ac.uk/rbf/PIGDATA/ (exmaple videos organized in test_data_prep/test_video directory) and use the preannotated info in the `behvaiour_15.npy` file for each video. The most important file to prepare data from the video and annotations is the `test_data_prep/create_slowfast_data_AVA.ipynb` . The code to do the training is in `test_data_run/train_PIGS.ipynb` . The highlighted file mentioned are highlighted below:

├── test_data_prep <br>
│   ├── CutVideosI.ipynb # cut a video into 1 frame/second (demo only, results not used) <br>
│   ├── CutVideosII.ipynb # show how to cut a video into 30 frames/second (demo only, results not used) <br>
│   ├── test_video # example videos with annotation files <br>
│   ├── create_slowfast_data_AVA.ipynb # MAIN code to prepare the relevant data in AVA format for SlowFast model training <br>
│   ├── test_data_run <br>
│       ├── train_PIGS.ipynb # # MAIN code to do the SlowFast model training <br>



