# jva-capture

[![PyPI](https://img.shields.io/pypi/v/jva-capture.svg)](https://pypi.org/project/jva-capture/)
![PyPI - Downloads](https://img.shields.io/pypi/dd/jva-capture)
![PyPI - Python Version](https://img.shields.io/pypi/pyversions/jva-capture)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Screen recording interface for the JVA01-Capture device using ffmpeg on macOS.

## Installation

```bash
pip install jva-capture
```

Or with uv:

```bash
uv add jva-capture
```

ffmpeg must be installed separately:

```bash
brew install ffmpeg
```

## Usage

```python
from jva_capture import JVACapture

# Basic usage
capture = JVACapture("output.mkv")
capture.start()
# ... run your experiment ...
capture.stop()

# As context manager
with JVACapture("output.mkv") as capture:
    # ... run your experiment ...
    pass
```

### Parameters

| Parameter | Default | Description |
|---|---|---|
| `output_path` | *(required)* | Path where video file will be saved |
| `device_name` | `"JVA01-Capture"` | Name of the AVFoundation capture device |
| `framerate` | `60` | Recording framerate (fps) |
| `preset` | `"medium"` | ffmpeg encoding preset (`ultrafast`, `fast`, `medium`, `slow`) |

## Requirements

- macOS (uses AVFoundation)
- Python >= 3.11
- ffmpeg installed and available in PATH
- JVA01-Capture device connected

## License

[MIT](LICENSE)
