# two-sigma-financial-modeling
kaggle competition: https://www.kaggle.com/c/two-sigma-financial-modeling

+ [forums](https://www.kaggle.com/c/the-nature-conservancy-fisheries-monitoring/forums)
+ [kernels](https://www.kaggle.com/c/the-nature-conservancy-fisheries-monitoring/kernels)

This dataset contains anonymized features pertaining to a time-varying value for a financial instrument. Each instrument has an id. Time is represented by the 'timestamp' feature and the variable to predict is 'y'. No further information will be provided on the meaning of the features, the transformations that were applied to them, the timescale, or the type of instruments that are included in the data. Moreover, in accordance with competition rules, participants must not use data other than the data linked from the competition website for the purpose of use in this competition to develop and test their models and submissions.

Data is saved and accessed as a .h5 file in the Kernels environment. We have used the .h5 file format instead of the standard .csv format to achieve faster read speeds. The training set file is available for download and offline modeling outside of Kernels. The test set is not available for download.

In addition to the data, you will need to familiarize yourself with the Kernels environment and the competition data API. The API is designed to prevent accessing data beyond the timestamp for which you are predicting and informs you which ids require predictions at which timestamps. The API also provides a "reward" for each timestamp, in the form of an average R value over the predicted values for the previous day. You may choose to use this reward to do reinforcement-style learning. Your code should expect and handle missing values.

We have setup the kernels environment such that the code structure you use for training on the test set (clicking "Run") will ideally work for submissions on the test set (clicking "Submit"). To achieve this, we have partitioned the training set such that the first half is provided as a training set at the start of a run, and the latter half is streamed through the API, as though it is a holdout set. In other words:
+ Run: first half of training set (split by time) provided initially, second half of training set used for API/predictions.
+ Submit: all of training set provided initially, test set used for API/predictions.

**Getting Started Tips**

+ Submissions must happen via a Script. Notebooks are available for exploratory analysis on the training set, but can not be used to submit.
+ Use the "Run" functionality in Kernels to check your method against the training set before you submit. Since this competition has an error limit per day, you'll want to eliminate basic syntax/typo errors before attempting to submit.
+ For more on how to make a submission, see the [submission instructions tab](https://www.kaggle.com/c/two-sigma-financial-modeling#submission-instructions). For an overview of the Kaggle Gym API, [follow this tutorial notebook](https://www.kaggle.com/jeffmoser/two-sigma-financial-modeling/kagglegym-api-overview).

### Evalution

Submissions will be evaluated on the R value between the predicted and actual values. The R value similar to the R squared value, also called the [coefficient of determination](https://en.wikipedia.org/wiki/Coefficient_of_determination).

**Negative R values are clipped at -1, i.e. the score you see will be `max(−1,R)`.** Additionally, if a submission errors for any reason, you will receive a simple "Error" status.

### Submission

Are you ready to enter Kaggle's inaugural Code Competition? Unlike our standard competitions, where submissions take the form of csv files, participants in Code Competitions will submit code through the Kernels platform. This code is then automatically executed on the test set. To help you make your first submission and get your name up on the leaderboard, we've put together some instructions and helpful pointers.

**Required Steps**

1. From the competition's page, click "Submit Model" on the right side of the competition menu bar. Note that you can also make a submission by clicking on "New Script" from the [Kernels tab](https://www.kaggle.com/c/two-sigma-financial-modeling/kernels).
2. Once you've reviewed and accepted the competition rules, a new script editor will open with Python code to make an all-zeros submission.
3. Choose a title for your kernel and enter your code in the editor. Remember, your kernel will be private to you unless you decide to share it later. When you're done, you can choose either:
+ "Run" to run your model against the training set. You may make unlimited runs.
+ "Submit" to run your model against the test set. Submissions are limited per day (see **Important Notes** below for details).
4 .Choosing "Submit" will take you to the leaderboard. Once your submission finishes running, your public leaderboard score and position are revealed.

**Kaggle Gym API Overview & Starter Tutorial**

Now that you've made your first submission, follow our tutorial demonstrating how to work with the [Kaggle Gym API for Code Competitions](https://www.kaggle.com/jeffmoser/two-sigma-financial-modeling/kagglegym-api-overview).

**Important Notes**

+ The compute constraints for this competition are:
    - Submission Limits: you have up to 2 submissions OR 5 error submissions per day. Hitting either limit will disable the ability to submit for the day. Errors are limited in this competition to prevent probing the private leaderboard through error status.
    - Time Limit: 20 minutes per exploratory run, 60 minutes for submissions
    - Memory Limit: 8 GB for run, 16 GB for submissions
+ Kernels are private to competitors by default. If you want to share your kernel, you can use the toggle in the editor to make it public. **Be aware that once you've made a kernel public, it cannot be made private again.**
+ Currently, the only language available for our first Code Competition is Python.
+ Kernels are run in [Kaggle's Python Docker container](https://github.com/Kaggle/docker-python). If you want to set up our Python container locally, read our [guide for getting started with containers](http://blog.kaggle.com/2016/02/05/how-to-get-started-with-data-science-in-containers/).
+ Your submission is officially timestamped at the time you submit it, not the time it finishes running. However, you can not select a submission for private leaderboard scoring until after it has scored. Do not wait until the competition deadline to submit and select!