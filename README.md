# Rolling Track Lab

Interactive classroom app for rolling a ball down a straight track and predicting its horizontal range after a downward launch.

## Run

No build step or dependencies. Open `index.html` in a browser, or serve this folder:

```sh
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Use

- Adjust ramp/downward launch angle (measured below horizontal), launch height above the landing level, release distance along the track, and rotational inertia.
- The shaded practice region ends at approximately **1.2 m** (roughly four feet); the longer-track region is for prediction.
- Enter measured release distances and horizontal ranges to overlay points on the theoretical curve. Edit or remove individual points.
- Measurements persist locally in the same browser. Export CSV to keep or share a copy; exported rows include the model settings at entry.
- Use the target-distance control to calculate the required release distance.

## Model

Release from rest, rolling without slipping, rotational inertia I = bMR², no rolling losses or air resistance, and the same angle for the straight track and downward launch. Default settings are 25°, 1.1 m launch height, and a solid sphere (b = 2/5). Gravity is 9.81 m/s².

The practice length is approximate, not a claim about cut precision. Set angle and height to the actual apparatus. Predictions outside the practice region are not measurements.

## Files

- `index.html`: interface and model explanations
- `style.css`: responsive layout
- `app.js`: physics, SVG plots, measurements, and CSV export

No student measurements are stored in this repository or sent to a server by this app. Browser storage is not a shared class dataset.
