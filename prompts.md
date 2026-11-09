# Engineering Journey & Prompt History: Form Photo Fixer

This document records the sequence of prompts, architectural design decisions, and testing iterations followed to build the **Autonomous Offline Form Photo Fixer** for the BSERC Internship (Week 2, Project 2).

---

## Prompt 1: Requirements Analysis & Preset Configuration
> **Prompt:**  
> "I need to build an offline image processing web tool called Form Photo Fixer. When students submit competitive exam forms (UPSC, SSC, GATE), forms reject photos/signatures that exceed strict dimensions (e.g. 3.5 x 4.5 cm) and file size limits (e.g. 50 KB).  
> Requirements:
> 1. Dual upload for passport photograph and signature.
> 2. At least 3 official presets with dimension and KB limits, citing official notices.
> 3. Interactive crop modal with face guide and signature baseline guide.
> 4. Iterative canvas-based compression engine that lands strictly under target KB.
> 5. Custom preset creator persisted in localStorage.
> 6. Single-click file downloads."

**Outcome:**  
Engineered `js/presets.js` containing 4 official presets (UPSC, SSC, GATE, IBPS) and `PresetManager` with `localStorage` CRUD support.

---

## Prompt 2: Iterative Canvas Compression Engine
> **Prompt:**  
> "Build `js/engine.js` with an automated binary-search / stepped canvas JPEG compression loop. It should measure generated Blob sizes in KB and step down quality smoothly to land just under target KB without visible blurriness. It must run 100% offline using native Canvas and Blob APIs."

**Outcome:**  
Engineered `PhotoFixerEngine.compressToTarget()`, achieving target KB compliance within 14 binary search steps and fallback scaling for noisy high-res camera captures.

---

## Prompt 3: Interactive Crop Modal & Visual Overlays
> **Prompt:**  
> "Implement an interactive crop modal supporting pan (mouse and touch) and zoom scaling. Render a dashed passport face guide (head oval, eye line, chin line occupying ~70% of frame) for photos, and a centered baseline guide for signatures."

**Outcome:**  
Engineered `renderCropCanvas()`, `drawFaceGuide()`, and `drawSignatureGuide()` with responsive coordinates and touch gesture listeners.

---

## Prompt 4: UI Assembly & Offline Verification
> **Prompt:**  
> "Create `index.html` and `css/style.css` featuring side-by-side photo and signature cards, real-time file size progress indicators, and custom preset modals. Verify that it functions completely in flight mode."

**Outcome:**  
Delivered standalone application with zero external CDNs, verified against large phone photo uploads and official notice rules.
