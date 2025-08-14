# 🟡 Yellow Car Detector

A web application that uses your camera to **detect yellow car bodies in real time**, determine the **shade of yellow**, and display the **HEX code** of the dominant color.  
Everything runs **locally in the browser** – no video is uploaded to any server. Perfect for playing the “Yellow Car” game with friends without arguments.

---

## 🚀 Features
- **Real-time analysis** of colors from your camera (WebRTC + JavaScript)
- Determines the dominant color in **HSV** and matches it to a palette of named yellow shades
- Displays the **shade name**, **HEX code**, **dominant HSV**, yellow coverage (%) and detection confidence (%)
- Optional **ROI mode** – draw a region of interest (e.g., only the car body)
- Adjustable thresholds for saturation (S) and brightness (V) for more accurate detection

---

## 🛠 Technology
- HTML, CSS, Vanilla JavaScript
- `getUserMedia` API for camera access
- Canvas API for image processing directly in the browser
- No backend – perfect for hosting on **Vercel Free**

---

## 📦 Deploying to Vercel
1. Open [Vercel](https://vercel.com/)
2. Import this repository
3. Framework Preset: **Other**
4. Output Directory: *(leave empty)*
5. Click **Deploy**

---


## 📜 License
MIT © 2025
