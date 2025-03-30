# 📄 Submission File Format

The submission should be a `.zip` file named [prediction.zip](./prediction.zip), which contains a CSV file named [prediction.csv](./prediction.csv).

In [prediction.csv](./prediction.csv), each row represents one video sample, with the following columns:


## Column Description
| Column | Description |
| - | -| 
| `vid` |	The unique video ID (corresponding to the video file name, e.g., 0003_01_0005.mp4). |
| `action_pred_1` ~ `action_pred_5`	|  The top-5 predicted labels at the action level, sorted by confidence (from highest to lowest). | 
| `body_pred_1` ~ `body_pred_5` | The top-5 predicted labels at the body level, sorted by confidence (from highest to lowest). | 

✅ Example

```
vid,action_pred_1,action_pred_2,action_pred_3,action_pred_4,action_pred_5,body_pred_1,body_pred_2,body_pred_3,body_pred_4,body_pred_5
0003_01_0005.mp4,51,49,35,14,19,2,2,3,1,2
```

In this example:

- The video ID is 0003_01_0005.mp4.

- The top-5 **action-level** predictions are: 51, 49, 35, 14, 19.

- The top-5 **body-level** predictions are: 2, 2, 3, 1, 2.