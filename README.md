# action-recognition
## 手勢辨識系統
### 參考來源：https://www.youtube.com/watch?v=doDUihpj6ro&t=8101s

How to do action recognition?
---
> 參考手勢辨識教學影片 
> https://www.youtube.com/watch?v=doDUihpj6ro&t=5902s
1. 設定三個手勢，一個手勢有30個小影片，而每一個小影片有30幀，每一幀又會有258個 keypoints 
2. 當我們路好這些影片之後，將這些節點丟進LSTM model 進行訓練。
3. 原設定為 2000 epoch，但是到 100 epoch時，accuracy就已經到1了
error during the action recognition
---
1. tensorflow cannot run on my jupyter notebook
> refer to the video to solve the problem 
> https://www.youtube.com/watch?v=oZjau-aUk0U&t=418s
2. 做完3個手勢的姿勢辨識後，發現會一直卡在right_hand_lift，但這並不符合預期結果，推測可能結果，第一個是我們錄right_hand_lift的時候是從下往上將手升起，因此模型輸入的節點中有一些是我們手還沒升起時的狀態。可能因此誤認為right_hand_lift的手勢。
> 新增一個手勢是 no_actoin
4. 影片中lag有點嚴重，將30幀改為18幀。
