# Rolling Track Lab

## Open the lab

**[Launch the public Rolling Track Lab](https://rolling-track-lab-pnord.paranord.chatgpt.site)**

Use this link for the classroom app; no download or local server is needed.

Interactive classroom app for rolling a ball down a straight track and predicting its horizontal range after a downward launch.

## Run locally (development)

No build step or dependencies. Open `index.html` in a browser, or serve this folder:

```sh
python3 -m http.server 8000
```

Then open http://localhost:8000. This address serves your local copy on your own computer; it is not the public classroom link.

## Use

- Adjust ramp/downward launch angle (measured below horizontal), launch height above the landing level, release distance along the track, and rotational inertia.
- The shaded practice region ends at approximately **1.2 m** (roughly four feet); the longer-track region is for prediction.
- Enter measured release distances and horizontal ranges to overlay points on the theoretical curve. Edit or remove individual points.
- Measurements persist locally in the same browser. Export CSV to keep or share a copy; exported rows include the model settings at entry.
- The graph initially extends to 2.5 m. The release slider spans 0–3 m; the numeric field and target solver support longer releases (up to 100 m).
- Set the target range beside the graph to see a horizontal dashed target line. This is synchronized with the inverse calculator below.
- Optional rolling resistance is off by default. When enabled, set a constant effective opposing deceleration in m/s².
- CSV exports include entry-time loss settings; older saved points are treated as resistance off with zero loss.

## Model

The default ideal model assumes release from rest, rolling without slipping, rotational inertia I = bMR², no rolling losses or air resistance, and the same angle for the straight track and downward launch. Default settings are 25°, 1.1 m launch height, and a solid sphere (b = 2/5). Gravity is 9.81 m/s².

With rolling resistance enabled, net downhill acceleration is `a = g sin(theta)/(1+b) - a_loss` and `v² = 2ad`. The loss parameter is an effective constant deceleration, not a friction coefficient. It affects only the ramp; air resistance remains neglected. If net acceleration is not positive, the app reports no launch/no flight and disables the target-release action. For positive acceleration, the inverse target calculation uses the same loss-adjusted model.

The practice length is approximate, not a claim about cut precision. Set angle and height to the actual apparatus. Predictions outside the practice region are not measurements.

## Files

- `index.html`: interface and model explanations
- `style.css`: responsive layout
- `app.js`: physics, SVG plots, measurements, and CSV export

No student measurements are stored in this repository or sent to a server by this app. Browser storage is not a shared class dataset.
