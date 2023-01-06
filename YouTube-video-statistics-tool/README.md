To use this YouTubeAPI class, you will need to have a YouTube Data API key. You can obtain one by following the instructions here.

1)[Create a YouTube AP](https://www.youtube.com/watch?v=N18czV5tj5o) <br>

2)[Get the channel_id from this website](https://commentpicker.com/youtube-channel-id.php) <br>

**Installation** <br>
You will need to have the following libraries installed in order to use this class:<br>
request<br>
pandas<br>
You can install these libraries using pip.<br>

```python
pip install requests 
pip install pandas
 ```
For example:<br>

Here are some examples of how to use this class:

```python
# Import the YouTubeAPI class
from YouTubeAPI import YouTubeAPI

# Set the API key and channel ID
api_key = "YOUR_API_KEY"
channel_id = "UC_CHANNEL_ID"

# Create an instance of the YouTubeAPI class
api = YouTubeAPI(api_key, channel_id)

# Get video data for all the videos in the channel
videos = api.get_channel_videos()

# Print the first 5 rows of the DataFrame
print(videos.head())

# Get statistics for a list of video IDs
video_id_list = ["VIDEO_ID_1", "VIDEO_ID_2", "VIDEO_ID_3"]
stats = api.get_video_stats(video_id_list)

# Print the first 5 rows of the DataFrame
print(stats.head())

# Get the comments for a list of video IDs
video_id_list = ["VIDEO_ID_1", "VIDEO_ID_2", "VIDEO_ID_3"]
comment = api.get_comments(video_id_list)

# Print the first 5 rows of the DataFrame
print(comment.head())


```



***Method Reference***

## YouTubeAPI(api_key, channel_id)

### Parameters:

| Name | Type | Description |
|------|------|-------------|
| api_key | str  | Your YouTube Data API key|
| channel_id|str | The ID of the YouTube channel you want to retrieve data for.|


## get_channel_videos()

### Returns:
A Pandas DataFrame containing the following columns:

|Name| Type | Description |
|-----|------|-------------|
|video_id| str  |The ID of the video.|
|video_title|str|The title of the video.|
|video_publishDate|str|The date the video was published (formatted as YYYY-MM-DD).



## get_video_stats(video_id_list)
Returns statistics for a list of YouTube videos specified by the video_id_list parameter.

### Parameters:

| Name | Type | Description |
|------|------|-------------|
| video_id_list | list  |A list of YouTube video IDs.|


### Returns:
A Pandas DataFrame containing the following columns:

|Name| Type | Description |
|-----|------|-------------|
|video_id| str  |The ID of the video.|
|video_viewCount|int|The number of views the video has received.|
|video_likeCount|int|The number of likes the video has received.|
|video_favoriteCount|int|The number of times the video has been marked as a favorite.|
|video_commentCount|int||The number of comments the video has received.|


## get_comments(video_id_list)
Returns comments for a list of YouTube videos specified by the video_id_list parameter.

### Parameters:

| Name | Type | Description |
|------|------|-------------|
| video_id_list | list  |A list of YouTube video IDs.|


### Returns:
A Pandas DataFrame containing the following columns:

|Name| Type | Description |
|-----|------|-------------|
|video_id| str  |The ID of the video.|
|comment_desc|str|Each comments on that specific video_id|







