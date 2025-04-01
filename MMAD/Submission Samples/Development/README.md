# 📄 Submission File Format

The submission should be a `.zip` file named [prediction.zip](./prediction.zip), which contains a CSV file named [prediction.csv](./prediction.csv).

In [prediction.csv](./prediction.csv), each row represents one micro-action proposal, with the following columns:


## Column Description
| Column | Description |
| - | -| 
| video_id | The unique ID of the video (e.g., `val0000`). |
|t_start | The predicted **start time** of the action in seconds (floating-point number). |
|t_end | The predicted **end time** of the action in seconds (floating-point number). |
|class | The predicted **action-level category** (integer label). |
|score | The **confidence score** of the prediction (ranging from 0 to 1). |


✅ Example

```
,video_id,t_start,t_end,class,score
0,val0000,0.9324134826660156,6.672196655273438,5,0.2297385185956955
```

In this example:

The prediction corresponds to video `val0000`.

The predicted action starts at 0.93 seconds and ends at 6.67 seconds.

The predicted `action-level category` is 5.

The prediction has a `confidence score` of `0.2297`.