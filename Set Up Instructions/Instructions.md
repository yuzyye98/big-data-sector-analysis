
The instructions are fairly straight forward to replicate our study. Below are the steps and resources we used in our project.

# Data source
We leveraged a subset of the Kaggle dataset [Amazon Product Review ( Spam and Non Spam)](https://www.kaggle.com/naveedhn/amazon-product-review-spam-and-non-spam) to conduct our project. Specifically, we focused on the `electronics.json` file, which contains around 7.5 millions rows of review data. 

# Steps to re-produce our results
1. Create a S3 bucket.
2. Extract the `electronics.json` file and upload the file to the bucket created in step 1.
3. Open Amazon SageMaker, and follow the steps [here](Build Amazon SageMaker notebooks backed by Spark in Amazon EMR) to use a SageMaker notebook instance along with Spark. One thing worth noting is that, since the `electronics,json` file is a large file, when setting up the SageMaker notebook, the Notebook instance type should have at least 8GB of memory and 32GB of volume size. In so doing, we could have enought memory to deal with all the calculation.
4. Modify the S3 location in the script in terms of where the location of the file is and where the analysis result should be stored.
5. Run the notebooks and the results we be saved to the designated location. With this huge amount of data, it takes around 30 min to finish the spam detection and takes around 1-2 hour to finish the LDA results.
6. Open Quicksight and import the S3 bucket, as shown in the video. Create a manifest file of AWS supported format as linked here: https://docs.aws.amazon.com/quicksight/latest/user/supported-manifest-file-format.html
