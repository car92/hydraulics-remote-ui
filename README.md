# Hydraulics Remote UI (BLE)

This is a single-file, mobile-friendly web UI that talks to your **Heltec LoRa V3 receiver** over **Bluetooth Low Energy** using Web Bluetooth.

## Deploy (GitHub Pages – free, HTTPS)

1. Create a **public** repo (e.g. `hydraulics-remote-ui`).
2. Upload `index.html` and this `README.md` to the repository root.
3. Go to **Settings → Pages**:
   - Source: **Deploy from a branch**
   - Branch: **main** and **/** (root)
4. Wait ~1 minute, then open:
   - `https://<your-username>.github.io/<repo-name>/`

> Web Bluetooth requires **HTTPS**, which GitHub Pages provides for free.

## Use

1. Open the site in **Chrome on Android**.
2. Tap **Connect (Bluetooth)** and choose **HydraulicsRX**.
3. Select a function tile and use the **Pump/Dump sliders**.
4. The page sends the same frames your TX uses, e.g. `S:3`, `S:10,F:3`, `S:12,F:3`.

## UUIDs (must match your RX firmware)

- Service: `0000f00d-0000-1000-8000-00805f9b34fb`
- CMD (Write Without Response): `0000f0c1-0000-1000-8000-00805f9b34fb`
- EVT (Notify): `0000f0e2-0000-1000-8000-00805f9b34fb`

## iPhone support

Safari’s Web Bluetooth is limited. For iPhone without Wi‑Fi, wrap this page in a tiny **Capacitor** app and use a BLE plugin, or switch the RX to **Wi‑Fi (STA) + WebSocket**. The UI doesn’t need changes.

## Safety notes

- Heartbeat: 70 ms while Pump/Dump is engaged.
- Watchdog/interlocks are enforced on the RX (recommended).

Enjoy!
