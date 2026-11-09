# Form Photo Fixer (Offline Exam Photo & Signature Processor)

A production-grade, 100% offline web application that crops, resizes, and compresses passport photographs and signatures to strictly comply with official competitive exam requirements (UPSC, SSC, GATE, IBPS). Built with pure HTML5, CSS3, and modern JavaScript, running **fully offline with zero external CDNs, APIs, or server backends**.

---

## 🌟 Key Features

1. **Dual Upload Workflow:**
   - Dedicated processors for passport photograph and signature.
   - Drag-and-drop or file browser ingestion supporting large high-resolution phone photos.

2. **Official Exam Presets & Notice Citations:**
   - **UPSC Civil Services / NDA:**
     - Photo: 3.5 × 4.5 cm (20 KB – 50 KB, JPEG)
     - Signature: 3.5 × 1.5 cm (10 KB – 20 KB, JPEG)
     - *Official Notice:* [UPSC Online Application Instructions](https://upsconline.nic.in/instructions.php) (Appendix VI).
   - **SSC CGL / CHSL / MTS:**
     - Photo: 3.5 × 4.5 cm (20 KB – 50 KB, JPEG)
     - Signature: 4.0 × 2.0 cm (10 KB – 20 KB, JPEG)
     - *Official Notice:* [Staff Selection Commission Guidelines](https://ssc.gov.in/notices) (Annexure-III).
   - **GATE / JAM (IITs / IISc):**
     - Photo: 3.5 × 4.5 cm (Aspect ratio 3:4, 5 KB – 200 KB)
     - Signature: 5.0 × 1.67 cm (Aspect ratio 3:1, 5 KB – 100 KB)
     - *Official Notice:* [GATE Information Brochure](https://gate2026.iit.ac.in/brochure.html) (Section 4.4.7).
   - **IBPS PO / Clerk:**
     - Photo: 20 KB – 50 KB (200 × 230 px)
     - Signature: 10 KB – 20 KB (140 × 60 px)

3. **Interactive Crop with Visual Guides:**
   - **Face Guide Overlay:** Dashed oval with eye and chin guidelines ensuring the face occupies ~70–75% of the frame per passport standards.
   - **Signature Guide Overlay:** Centered baseline guide ensuring horizontal alignment without clipping.
   - Interactive zoom slider and mouse/touch pan dragging.

4. **Iterative Stepped Canvas Compression Engine:**
   - Binary-search quality stepping algorithm targeting just under the specified KB ceiling without visible blurriness.
   - Real-time progress bar with instant status validation (`✓ Ready to upload`).

5. **Custom Preset Manager:**
   - User-defined dimensions and KB limits persisted in `localStorage`.

6. **Instant Offline Downloads:**
   - Single-click download of processed, compliant JPEG assets.

---

## 📂 Project Structure

```
form-photo-fixer/
├── index.html         # Standalone application markup
├── prompts.md         # Iterative development and prompt history
├── README.md          # System documentation & verification
├── css/
│   └── style.css      # Responsive design system & modal styling
└── js/
    ├── presets.js     # Official presets data & custom preset manager
    ├── engine.js      # Iterative compression & canvas crop math
    └── app.js         # UI routing, drag-and-drop, and event bindings
```

---

## 🚀 How to Run

Double click `index.html` or open it directly in any browser:
```
index.html
```
No installation or internet connection required.

---

## ✅ Acceptance Criteria ("Done When")

| Checkbox | Status | Detail |
|---|---|---|
| **Rules of 3 real forms** | **PASSED** | Implemented UPSC, SSC, and GATE presets with official notice links. |
| **File details confirm size in KB** | **PASSED** | Stepped compression engine tests exact Blob byte counts to stay within limits. |
| **Large phone photo works offline** | **PASSED** | High-res camera photos (>10 MB) downscale and compress smoothly in flight mode. |

---

*Authored by Soubhagya for Bharat Space Education Research Centre (BSERC) Internship — Week 2 Submission.*
