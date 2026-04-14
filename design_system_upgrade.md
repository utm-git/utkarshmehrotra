# 1. COLOR SYSTEM (Vercel/Linear Inspired)

To achieve that premium, high-signal engineering look, we abandon generic bright blues and adopt a high-contrast monochromatic base with a single, highly intentional accent color.

*   **Primary Accent:** `#0055FF` (A deep, electric "System Blue" that screams high-end tech. Replacing the generic Tailwind `#3B82F6`).
*   **Base Background:** `#FAFAFA` (Extremely subtle off-white to reduce eye strain).
*   **Card/Surface Background:** `#FFFFFF` (Pure white for raised elements).
*   **Primary Text:** `#111111` (Near black, stark and readable).
*   **Secondary Text:** `#666666` (Neutral gray for dates, roles, and body text that shouldn't compete with headers).
*   **Subtle Borders:** `#EAEAEA` (For dividing sections without drawing attention).

---

# 2. TYPOGRAPHY

Currently, `Inter` is used everywhere. To elevate to SDE3 aesthetic, we introduce a tighter, more structured headline font while keeping `Inter` for readability in paragraphs.

*   **Heading Font:** `Geist` (by Vercel) or system-ui `SF Pro Display`. Tightly tracked (letter-spacing: -0.02em).
*   **Body Font:** `Inter` or `Geist Mono` for tech stacks/metrics.
*   **Hierarchy:**
    *   **H1 (Hero):** 2.75rem, Font Weight 600, Tracking -0.03em.
    *   **H2 (Section Headers):** 0.85rem, Font Weight 500, All-caps, Tracking 0.08em, Color `#666666`. (Acts as a subtle label rather than a shouting header).
    *   **Body:** 1rem, Line Height 1.6, Color `#444`.

---

# 3. LAYOUT & SPACING

The current design feels slightly cramped. We need "breathable" constraints.

*   **Max Width:** Increase slightly to `760px` to give dense architectural descriptions more breathing room.
*   **Vertical Section Rhythm:** Expand typical section margins from `56px` to a massive `120px` or `4rem`. This forces the reader to pause between concepts.
*   **Alignment:** Keep everything fiercely left-aligned. Flush-left creates a brutalist, highly structured reading line typical of high-end API documentation (like Stripe).

---

# 4. COMPONENT DESIGN & SNIPPETS

### A. The Hero Section
Remove the boxed borders on your links. The focus should be on your metrics.

```css
/* Hero Snippet */
.hero {
  padding: 120px 0 80px;
  border-bottom: none; /* Let whitespace do the dividing */
}

.hero h1 {
  font-family: 'SF Pro Display', 'Inter', sans-serif;
  font-size: 2.5rem;
  font-weight: 600;
  letter-spacing: -0.04em;
  color: #111;
  margin-bottom: 0.5rem;
}

.hero .role {
  color: #666;
  font-size: 1.1rem;
}

/* Redefined Primary CTA */
.btn-primary {
  background: #111; /* Black button feels more premium than loud blue */
  color: #fff;
  padding: 10px 20px;
  font-size: 0.9rem;
  border-radius: 6px;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  box-shadow: 0 4px 14px 0 rgba(0, 0, 0, 0.1);
}
.btn-primary:hover {
  transform: translateY(-1px);
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.15);
}
```

### B. Experience Section (The "Timeline" approach)
Instead of floating blocks, ground the experience with a subtle left border to indicate timeline progression, a hallmark of clean developer portals.

```css
/* Experience Snippet */
.exp-item {
  position: relative;
  padding-left: 24px;
  border-left: 2px solid #eaeaea;
  margin-bottom: 3rem;
}

/* The timeline "dot" */
.exp-item::before {
  content: '';
  position: absolute;
  left: -5px; /* Centers dot on the 2px border */
  top: 6px;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: #EAEAEA;
  transition: background 0.2s ease;
}

.exp-item:hover::before {
  background: #0055FF; /* Subtle interaction when reading a specific job */
  box-shadow: 0 0 0 4px rgba(0, 85, 255, 0.1);
}
```

### C. System Design / Project Cards
Instead of top-border highlights, move to an ultra-clean "Linear-style" card with an inset shadow or micro-border.

```css
.card {
  background: #FFFFFF;
  border: 1px solid rgba(0,0,0,0.06);
  border-radius: 12px;
  padding: 32px;
  box-shadow: 0 1px 3px rgba(0,0,0,0.02);
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.card:hover {
  border-color: rgba(0, 85, 255, 0.2);
  box-shadow: 0 8px 30px rgba(0,0,0,0.04);
}
```

### D. Tech Stack
Ditch the visual clutter of 15 "pill/bubble" tags. They look junior. Senior engineers list tech cleanly. Use a monospace font for technologies to signal a developer environment.

```css
.tech-stack {
  font-family: 'Geist Mono', 'SF Mono', monospace;
  font-size: 0.85rem;
  color: #666;
  line-height: 1.8;
  word-spacing: 0.5rem;
}
/* Example Output: Java · Spring_Boot · Kafka · AWS_ECS */
```

---

# 5. VISUAL HIERARCHY (Highlighting Metrics)

When you write "100K+ writes/sec" or "$150K infrastructure savings", **do not just bold it**. Treat it like an inline badge or use your accent color.

```css
/* Use this class on your scale metrics */
.metric {
  color: #0055FF;
  font-weight: 500;
  background: rgba(0, 85, 255, 0.05); /* Very subtle highlight */
  padding: 0px 4px;
  border-radius: 4px;
}
```

---

# 6. INTERACTIONS

Keep it almost invisible.
*   **Nav Links:** A fade-in text color change from `#888` to `#111`. Drop the animated bottom border line; it feels a bit dated. Just pure text fading.
*   **Scroll:** Keep the current smooth intersection observer, but reduce the `translateY(12px)` in your `.reveal` animation to `translateY(6px)` and shorten the duration from `0.8s` to `0.5s` for a snappier, less dramatic reveal.

---

# 7. WHAT TO REMOVE (Crucial)

1.  **Remove "Skills" Bubbles:** Replace with the clean monospace block described above.
2.  **De-emphasize Education:** Put Education at the absolute bottom in small gray text. At SDE3, nobody is hiring you for your BTech; they are hiring you for the 50TB database migration.
3.  **Remove Boxed Nav Buttons:** The navigation bar should be invisible until scrolled, or simply float as bare text links without the sticky background blur unless absolutely necessary.
4.  **Remove Sub-text Tags in Hero:** "Real-time systems · Distributed platforms" under the Hero. Replace this with the single, piercing SDE3 Summary text we generated previously.

---

# NEXT STEPS
If you like these design adjustments, I can inject both the content from our last step AND these new CSS/Component designs directly into your `index.html` file right now in the backend. Let me know!
