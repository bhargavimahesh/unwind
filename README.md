# Unwind — breathe to disentangle

A biofeedback game. Break the seals in order (1 → A → 2 → B …) before time runs out while a snare
creeps across the screen. It grows with your stress, read live from a Polar H10 heart-rate strap,
and only withers when you slow down and breathe.

**Play:** open the GitHub Pages link for this repo in desktop Chrome or Edge.

## How it works

- **Sensor:** Polar H10 over Web Bluetooth (standard Heart Rate service, RR intervals). No app or SDK needed.
  The page must be served over https or from localhost.
- **Calibration:** 60 s of rest records your baseline heart rate and HRV (RMSSD).
- **Stress:** half heart rate above baseline, half the drop in RMSSD below baseline, over the last 16 beats.
- **The snare:** vines grow from the edges, branch, curl around the seals you need next and pulse with
  every heartbeat. Thrashing the mouse or clicking the vines makes them tighten. When you calm down they
  wilt and retract, and a calm hand slips straight through them.
- **No sensor?** Choose *Play with a simulated heart*: the task raises stress, hold <kbd>Space</kbd> to breathe.

Keys: <kbd>D</kbd> debug overlay · <kbd>M</kbd> mute · <kbd>B</kbd> breathing guide (auto / on / off).

## Run locally

```bash
python -m http.server 8642
```

Then open http://localhost:8642 in Chrome or Edge.
