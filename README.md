# Yellow Car Detector (Realtime, client-side)

Jednoduchá **statická webová** appka, která v reálném čase přes kameru detekuje, zda je v záběru **žlutá karoserie auta**, a vypíše **odstín žluté** i **HEX kód** dominantní barvy. Vše běží **lokálně v prohlížeči** (žádný upload na server), takže je to ideální na **Vercel (free)**.

## Rychlý deploy na Vercel (free)
1. Stáhni ZIP z chatbota a rozbal do složky.
2. Běž na https://vercel.com/new → zvol **Upload** (ne Git), nahraj obsah složky (musí obsahovat `index.html`).
3. Potvrď **Framework Preset: Other** a **Output Directory: /** (prázdné).
4. Deploy → za pár sekund dostaneš **https** URL. Hotovo.

## Použití
- Klikni **Spustit kameru** (na iOS to vyžaduje HTTPS + klik).
- Volitelně zapni **ROI režim** a myší vyznač obdélník kolem karoserie.
- Posuvníky **S** (saturace) a **V** (jas) doladí prahy. Žlutá je definována jako **H ∈ [20,38] (OpenCV škála 0–179)** plus minimální S a V.
- **Min. pokrytí žlutou** říká, jaká část ROl musí být žlutá, aby se vyhlásilo „ŽLUTÉ ✅“.
- Výstup: **odstín** (pojmenovaná žlutá), **HEX**, **dominantní HSV**, **jistota (%)** a **pokrytí (%)**.

## Poznámky
- Výpočet je **rychlý**: zpracování běží na zmenšeném snímku 320 px na šířku a subsamplingu pixelů.
- Odlesky / okna jsou částečně potlačeny požadavkem na **S** a **V**.
- Mapování na názvy odstínů se dělá v **CIELAB** (ΔE) na malou paletu (Canary, Lemon, Amber, ...).

## Omezení a tipy
- Bez extra ML modelu aplikace **detekuje „žlutost“**, ne „auto“ – ideálně vyznač **ROI** kolem karoserie.
- Silně oranžové nebo zlaté laky můžou spadat na hranu. V tom případě posuň **H** prah rozšířením (kódově je to jednoduché).
- Pokud chceš **model na detekci auta**, můžeš přidat on‑device YOLO (ONNX/TFLite) a masku aplikovat jen na karoserii.

## Lokální spuštění (bez Vercelu)
Stačí otevřít `index.html` přes jednoduchý server:

```bash
python3 -m http.server 8080
# otevři http://localhost:8080
```

## Licenční info
MIT. Vytvořeno 2025-08-14.
