# Raspberry Pi Runtime Code

This directory keeps the Raspberry Pi-side runtime code used in this project:

- `app.py`: Flask-based web control entry.
- `base_ctrl.py`: chassis and lower-controller command helper.
- `cv_ctrl.py`: OpenCV/MediaPipe vision control helper.
- `templates/`: web UI assets.
- `models/`: runtime CV model files referenced by `cv_ctrl.py`.

The original Waveshare Jupyter tutorial notebooks are intentionally not kept in this GitHub showcase repository, because they are vendor learning materials rather than project-specific implementation.
