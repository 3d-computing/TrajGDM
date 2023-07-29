# TrajGDM
> This is the official Code for ***Simulating Human Mobility with a Generative Trajectory Generation Model.\***

## Datasets

Two datasets are used to evaluate the performance of the model. 

**T-Drive:** The dataset collected the real taxi GPS trajectory in Beijing, China. It contains the trajectory of 10,357 taxis during the period of Feb. 2 to Feb. 8, 2008. The average sample frequency is 2.95 minutes. Considering the data missing problem, we resampled the location of every taxi for every 5 minutes, so all trajectories in the dataset have a fixed time interval. We extracted the positioning points in the six-ring road, which account for 98.2% of all points in the dataset. Then the region in the six-ring road is divided into 27*27 grids by the square with 2000 meters edge length, which was decided by the mobility frequency and averaged moving distance in the dataset. Eventually, there are 169,984 trajectories recorded. 

**Geo-life:** The dataset was collected from 182 people. The GPS trajectories record their mobility activity over 5 years. We also resampled all trajectories into a 5 minutes time interval and extracted points in six-ring road. Considering the mobility activity is relatively weak, the division is set as 500 meters, so there are 110*110 grids in total. At last, there are 79,360 trajectories left.

## How to Run the Code

The training dataset is used for training the trajectory generating model and evaluate models’ performance in generation. The testing dataset if used for evaluating the performance of zero-shot predicting and reconstructing. 

``` bash
1. Run runner/trainer.py to train a TrajGDM for T-Drive dataset. 
2. Run runner/trainer_geolife.py to train a TrajGDM for Geo-Life dataset.
3. Run runner/generation_eval.py to generate a synthesized trajectory dataset and evaluate its similarity with the real one using 5 metrics from the paper.
4. Run runner/zeroshot_eval.py to predict and reconstruct a trajectory with a trained TrajGDM model.
```



## Some Results

![3](https://hcimage-1253324558.cos.ap-beijing.myqcloud.com/uPic/3.gif)

![3](https://hcimage-1253324558.cos.ap-beijing.myqcloud.com/uPic/1.gif)
