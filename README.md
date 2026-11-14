# FLAMEGUARD — Local Python + Web Dashboard

## Contents
- `index.html` — responsive frontend, interactive spacecraft canvas, controls, charts, logs
- `app.py` — Flask REST API on port 8080
- `requirements.txt` — Python dependency
- `README.md` — setup instructions

## Run on Windows
1. Install Python 3.10+ from https://www.python.org/downloads/
2. Extract the ZIP.
3. Open the extracted `FLAMEGUARD` folder.
4. In the folder address bar, type `cmd` and press Enter.
5. Run:

   ```bash
   py -m venv .venv
   .venv\Scripts\activate
   pip install -r requirements.txt
   py app.py
   ```

6. Open http://127.0.0.1:8080 in Chrome or Edge.

## Run on macOS / Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python app.py
```

Then open http://127.0.0.1:8080.

## API endpoints
- `GET /api/health` — backend health check
- `GET /api/live-telemetry` — synthetic telemetry packet
- `POST /api/simulate` — calculate a demo result from submitted controls
- `POST /api/reset` — reset demo stream counter
- `GET /api/sample` — return a sample telemetry packet

## Important model limitation
This project is an educational prototype. The Python service generates synthetic data and uses a deliberately simplified illustrative scoring formula. It is **not** an AI model, validated combustion-physics solver, NASA software, real sensor integration, fire-safety certification, or operational spacecraft hazard predictor. Do not use its output for real-world safety decisions.

## Free static hosting
The frontend can be hosted as a static site on GitHub Pages or Vercel, but a static host does not run this local Flask service. To keep the REST API working online, deploy `app.py` to a Python-capable host and configure the frontend API base URL to that service's HTTPS address. For a simple local demo, run the Flask server and open the local URL above.


## Animated spacecraft visualization
The spacecraft cutaway now drifts through a starfield with parallax, subtle attitude motion, animated engine exhaust, metallic hull details, and solar arrays. Select a compartment to localize the simulated fire, glowing hull damage, sparks, and smoke to that section. The animation is a visual explanation layer; it is not a physical spacecraft model or a validated fire-propagation simulation.
