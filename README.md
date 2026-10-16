# Teach the Computer Your Hand Gestures

A no-code hand gesture detection lab for Computer Vision. Train your own gesture model in the browser, test it, and connect each gesture to an action.

## Pipeline

```
Camera frame -> Hand landmarks -> Gesture classifier -> Prediction -> Action
```

| Stage | In this project |
|---|---|
| Input | Webcam frame |
| Features | 21 hand landmarks from MediaPipe Hands, made relative to the wrist and scaled so distance does not matter |
| Model | k-nearest-neighbours classifier that learns from your recorded examples |
| Prediction | Gesture name and confidence for each class |
| Action | IF / THEN rules (Start / Move, Stop, Change mode, Confirm) |

## How to use

1. Click **Start camera** and allow access.
2. Hold **Hold to record** for each class (Open palm, Fist, Peace) while moving your hand slightly. Aim for 40 to 60 examples per class.
3. Add the 4th class (Thumbs up) only once the first three are reliable.
4. Watch the confidence bars in **Test the prediction**.
5. Try to break it: turn, move away, change light, change background, move fast.
6. Add better examples for the failure and test again.
7. Choose an action for each gesture.

