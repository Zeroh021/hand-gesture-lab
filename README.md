# Teach the Computer Your Hand

A no-code hand gesture detection lab for Grade 11 Computer Vision. Train your own gesture model in the browser, test it, and connect each gesture to an action.

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

## Run locally

Open `index.html` through a local server (browsers block the camera on plain `file://` in some cases):

```
python -m http.server 8000
```

Then visit http://localhost:8000

## Publish on GitHub Pages

1. Create a new repository and upload `index.html` and `README.md`.
2. Go to **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`.
4. After a minute your app is live at `https://<your-username>.github.io/<repo-name>/` (GitHub Pages uses https, which the camera needs).

## Notes

- Everything runs in your browser. No video or data leaves your computer.
- "Save model" stores your examples in this browser only (localStorage).
- Uses MediaPipe Hands from the jsDelivr CDN, so it needs an internet connection.
- Works best with one hand, good lighting, and the same hand you trained with.
