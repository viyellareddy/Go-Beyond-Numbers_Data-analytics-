
# TikTok Project: Exploratory Data Analysis

## Dataset

This project uses a dataset called `tiktok_dataset.csv`. It contains synthetic data created for this project in partnership with TikTok. 

### Data Dictionary

The dataset contains 19,383 rows and 12 columns. Each row represents a different published TikTok video in which a claim/opinion has been made.

| Column Name               | Type  | Description                                                                                                                   |
|---------------------------|-------|-------------------------------------------------------------------------------------------------------------------------------|
| #                         | int   | TikTok assigned number for video with claim/opinion.                                                                           |
| `claim_status`            | obj   | Whether the published video has been identified as an “opinion” or a “claim.” In this dataset, an “opinion” refers to an individual’s or group’s personal belief or thought. A “claim” refers to information that is either unsourced or from an unverified source. |
| `video_id`                | int   | Random identifying number assigned to video upon publication on TikTok.                                                        |
| `video_duration_sec`      | int   | How long the published video is measured in seconds.                                                                           |
| `video_transcription_text`| obj   | Transcribed text of the words spoken in the published video.                                                                   |
| `verified_status`         | obj   | Indicates the status of the TikTok user who published the video in terms of their verification, either “verified” or “not verified.”  |
| `author_ban_status`       | obj   | Indicates the status of the TikTok user who published the video in terms of their permissions: “active,” “under scrutiny,” or “banned.”  |
| `video_view_count`        | float | The total number of times the published video has been viewed.                                                                 |
| `video_like_count`        | float | The total number of times the published video has been liked by other users.                                                   |
| `video_share_count`       | float | The total number of times the published video has been shared by other users.                                                  |
| `video_download_count`    | float | The total number of times the published video has been downloaded by other users.                                              |
| `video_comment_count`     | float | The total number of comments on the published video.                                                                          |

## Project Structure

The project follows the PACE problem-solving framework:

1. **Plan**
2. **Analyze**
3. **Construct**
4. **Execute**

### 1. Plan

#### Tasks:

- **Imports, Links, and Loading**: Import necessary libraries and load the dataset.
- **Data Exploration and Cleaning**: Inspect and clean the dataset.
- **Select Visualization Types**: Choose appropriate visualization types for data analysis.

### 2. Analyze

#### Tasks:

- **Data Exploration and Cleaning**: 
  - Display and examine the dataset using `.head()`, `.info()`, `.describe()`.
  - Handle missing data and identify outliers.
- **Assess Data Types**: Verify data types of columns in the dataset.

### 3. Construct

#### Tasks:

- **Build Visualizations**:
  - Create various visualizations using Matplotlib and Seaborn to understand data distribution and relationships:
    - Box plots
    - Histograms
    - Scatter plots
    - Pie charts
- **Determine Outliers**: Identify and handle outliers using Interquartile Range (IQR) and median calculations.

### 4. Execute

#### Tasks:

- **Results and Evaluation**:
  - Summarize findings and insights from the visualizations.
  - Address any additional questions or aspects uncovered during the analysis.
- **Conclusion**: Present a professional summary of the analysis, emphasizing the importance of EDA and potential next steps.

## Files and Directories

- `notebook.ipynb`: The Jupyter notebook containing all the code and visualizations.
- `tiktok_dataset.csv`: The dataset used for analysis.
- `README.md`: This readme file.

## How to Run the Project

1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. **Set Up the Environment**:
   - Create a virtual environment and activate it:
     ```bash
     python -m venv venv
     source venv/bin/activate  # On Windows use `venv\Scripts\activate`
     ```
   - Install the required packages:
     ```bash
     pip install -r requirements.txt
     ```

3. **Run the Jupyter Notebook**:
   ```bash
   jupyter notebook
   ```
   - Open `notebook.ipynb` and run all cells to see the analysis and visualizations.

## Key Insights and Visualizations

### Box Plots

- **Video Duration**: The video durations are uniformly distributed between 5 and 60 seconds.
- **Video View Count**: Most videos have fewer than 100,000 views, with a right-skewed distribution.
- **Video Like Count**: Similar to view count, with fewer videos having very high like counts.
- **Video Comment Count**: Majority of videos have fewer than 100 comments.
- **Video Share Count**: Most videos have fewer than 10,000 shares.
- **Video Download Count**: Majority of videos were downloaded fewer than 500 times.

### Histograms

- **Video Duration**: Uniform distribution from 5 to 60 seconds.
- **Video View Count**: Heavily right-skewed with many videos having fewer than 100,000 views.
- **Video Like Count**: Right-skewed with a taper at higher like counts.
- **Video Comment Count**: Very right-skewed, most videos have fewer than 100 comments.
- **Video Share Count**: Skewed to the right, most videos have fewer than 10,000 shares.
- **Video Download Count**: Right-skewed, most videos were downloaded fewer than 500 times.

### Scatter Plots

- **Video View Count vs. Like Count**: Positive correlation, higher view counts generally correlate with higher like counts.

### Pie Charts

- **Total Views by Video Claim Status**: Claim videos dominate overall view counts despite a similar number of claim and opinion videos in the dataset.

## Results and Findings

- **Outliers**: Significant number of outliers in view counts, like counts, share counts, download counts, and comment counts. 
  - Number of outliers:
    - Video view count: 2343
    - Video like count: 3468
    - Video share count: 3732
    - Video download count: 3733
    - Video comment count: 3882

- **Claim vs. Opinion Videos**: 
  - Claim videos generally receive higher engagement (views, likes, comments, shares, downloads) compared to opinion videos.
  - Verified users are more likely to post opinions than claims.
  - Authors of claim videos are more likely to be under review or banned compared to those posting opinion videos.
  - Median view counts for non-active authors (those under review or banned) are significantly higher than for active authors.

## Executive Summary

- **Data Distribution**: The dataset contains highly skewed distributions for engagement metrics.
- **Outliers**: Numerous outliers indicate videos with exceptionally high engagement, typical for viral content.
- **Claims vs. Opinions**: Claim videos receive higher engagement and are more likely to be posted by non-active authors. Verified users tend to post opinion videos more frequently.

## Conclusion

Exploratory Data Analysis is essential for understanding the dataset and preparing it for modeling. The visualizations created provide valuable insights into the TikTok dataset, highlighting key differences between claim and opinion videos and the impact of various metrics on video performance. Future steps include further investigation into distinctive characteristics of claim vs. opinion videos and refining predictive models based on these insights.
