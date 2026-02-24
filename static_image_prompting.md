# AI Static Image Prompting Guide

## 1. Core Principle

Modern diffusion models do not physically simulate camera optics or lighting physics. When you specify "f/2.8 aperture" or "85mm lens," the model matches **aesthetic patterns** associated with those terms in its training data, not the underlying physics. This distinction is critical: parameters work through *learned stylistic association*, not optical computation.

**Implication:** Concrete, specific descriptors outperform vague aesthetic terms because they have lower entropy—they point to narrower, more consistent visual patterns in the training corpus. "Golden hour lighting" retrieves a well-defined aesthetic; "beautiful lighting" retrieves everything and nothing.

---

## 2. High-Impact Parameter Categories

### Lighting & Illumination

**What it controls:** Light direction, quality, color temperature, shadow behavior, and mood.

**Why it matters:** Lighting is the single highest-leverage parameter category across all tested models. It produces the most dramatic, consistent improvement to realism and visual coherence. Every major source—official documentation, practitioner guides, and academic research—converges on this finding.

**High-leverage parameters:**
- **Golden hour** — Warm, directional light with long shadows (universally recommended)
- **Rembrandt lighting** — Triangular highlight under eye (high drama, but may pull toward painterly aesthetics)
- **Rim lighting / backlighting** — Glowing outline separating subject from background
- **Cinematic lighting** — Broad signal for dramatic, multi-source illumination
- **Studio lighting / key light** — Strong, directed illumination
- **Natural conditions** — Overcast (soft diffusion), foggy (atmospheric mystery), sunny (hard shadows)

**Example usage:**  
`portrait of a woman, Rembrandt lighting, soft volumetric rays in background`

---

### Composition & Framing

**What it controls:** Subject placement, camera distance, viewing angle, and spatial organization.

**Why it matters:** Framing terms provide reliable structural control. Aspect ratio is a hard constraint that directly shapes the canvas and influences perceived style (vertical formats in DALL-E 3 trigger cellphone aesthetics; 16:9 signals cinematic framing).

**High-leverage parameters:**
- **Aspect ratio** — 16:9 (cinematic), 3:2 (photographic), 1:1 (social/editorial)
- **Shot types** — Extreme close-up, close-up, medium shot, full body shot, establishing shot
- **Camera angles** — Eye level, low angle, bird's eye view, side view, back view
- **Framing descriptors** — Centered composition, rule of thirds, bilaterally symmetrical

**Example usage:**  
`man in doorway, medium shot, low angle, centered composition, 16:9`

---

### Optics & Lens Physics

**What it controls:** Perspective distortion, depth of field aesthetics, focal compression, and perceived professionalism.

**Why it matters:** Focal length keywords produce visible compositional changes through learned associations, despite models not simulating actual optics. These work best in Midjourney and Stable Diffusion; reduced effect in DALL-E 3 and Firefly.

**High-leverage parameters:**
- **Focal lengths** — 14–24mm (wide, distorted), 85mm (portraits, natural compression), 200mm+ (telephoto, diminishing returns above this)
- **Depth of field** — "Shallow depth of field," "bokeh," "f/1.4" (aesthetic cue, not physical)
- **Camera bodies** — Sony Alpha a1, Hasselblad X1D II (shifts color science and perceived quality)
- **Film stocks** — Kodak Portra 400 (warm skin tones), Fujifilm Velvia 50 (vivid saturation), Cinestill 800T (cinematic tungsten look), Ilford HP5 (B&W contrast)

**Example usage:**  
`portrait, 85mm lens, shallow depth of field, Kodak Portra 400`

**Warning:** Plain-language terms like "close-up" or "wide shot" often achieve equal or better results than exact focal lengths.

---

### Material & Surface Detail

**What it controls:** Texture specificity, physical realism, tactile quality.

**Why it matters:** Naming specific materials prevents generic, plasticky defaults and adds grounded physicality. Particularly critical for portraits (prevents airbrushed skin) and product photography.

**High-leverage parameters:**
- **Skin descriptors** — Visible pores, slight blemishes, catchlight in eyes, fine wrinkles
- **Surface qualities** — Brushed metal, weathered stone, matte finish, translucent cellophane, rough fabric
- **General rule** — More specific always outperforms more generic

**Example usage:**  
`close-up of leather jacket, visible grain texture, worn patina, brushed metal zipper`

---

### Environment & Atmosphere

**What it controls:** Spatial depth, mood, air quality, environmental context.

**Why it matters:** Atmospheric terms consistently produce visible effects and work reliably across all models. They add depth and environmental realism.

**High-leverage parameters:**
- **Volumetric effects** — Volumetric lighting, volumetric fog, god rays, crepuscular rays
- **Weather/time** — Overcast, foggy, hazy, sunny, morning fog, dusk
- **Atmospheric depth** — Haze, mist, atmospheric perspective

**Example usage:**  
`forest scene, volumetric fog filtering through trees, morning light, atmospheric haze`

---

### Rendering & Style Constraints

**What it controls:** Genre signals, technical aesthetic, quality biasing.

**Why it matters:** These parameters are the most misunderstood and overused category. They function as training-data filters, not quality controls. Use sparingly and with intention.

**High-leverage parameters:**
- **Medium specification** — Photograph, editorial photography, cinematic still, oil painting, digital illustration
- **Intentional rendering** — "Octane render" (3D aesthetic, works *against* photorealism)
- **One quality tag** — 8K (sufficient alone; stacking is wasteful)

**Low-impact/avoid:**
- Quality stacks ("hyper detailed, insanely detailed, ultra realistic") — diminishing returns
- "Trending on ArtStation" — negligible effect when other modifiers present
- Exact numerical camera settings (f/2.8, ISO 400) — not physically simulated

**Example usage:**  
`editorial photograph, natural lighting, 8K`

**Critical finding:** Negative prompts ("low quality, blurry, distorted, oversaturated") more reliably improve output than positive quality boosters.

---

## 3. Minimum Effective Parameter Set

**The smallest set of parameters that consistently improves realism and control:**

1. **Lighting condition** (golden hour, Rembrandt lighting, studio lighting)
2. **Shot type/framing** (close-up, medium shot, wide shot)
3. **Aspect ratio** (16:9, 3:2, 1:1)
4. **Medium/style descriptor** (photograph, editorial, cinematic)
5. **Subject specificity** (detailed physical description)

**Five-element structure:**
```
[Specific subject with physical details], [shot type], [lighting condition],
[one camera/medium reference], [atmosphere or mood]
```

**Example:**
```
34-year-old man with weathered skin and gray-streaked beard standing in doorway,
medium shot, Rembrandt lighting, 85mm lens, morning fog filtering through background
```

This covers parameters with the strongest evidence of consistent impact while avoiding token waste on low-impact modifiers.

---

## 4. Parameter Interaction Notes

### Strong positive interactions:
- **Lighting + atmosphere** — "Golden hour" + "volumetric fog" compounds dramatic effect
- **Focal length + shot type** — "85mm" + "medium shot" reinforces portrait conventions
- **Film stock + lighting** — "Kodak Portra 400" + "soft natural light" compounds warm aesthetic

### Common conflicts:
- **Contradictory rendering engines** — Mixing "photorealistic" + "Octane render" creates aesthetic confusion
- **Resolution stacking** — "8K + 4K + ultra HD" wastes tokens; one tag suffices
- **Quality term redundancy** — "Highly detailed + intricate details + fine details" provides no additional signal

### Model-specific sensitivities:

**Midjourney & Stable Diffusion:**
- High sensitivity to camera/film references
- Strong response to lighting terms
- Focal length keywords produce visible changes

**DALL-E 3:**
- GPT-4 rewrites all prompts (reduces direct parameter control)
- Aspect ratio affects compositional style (vertical = cellphone aesthetic)
- Camera references have reduced effect

**Adobe Firefly:**
- Trained on Adobe Stock (not web-scraped data)
- Camera/film references have minimal effect
- Lighting terms remain effective

**SD3.5 / Flux (T5-based):**
- Accept longer prompts (>77 tokens)
- Natural language descriptions work better than keyword lists
- Quality tags increasingly unnecessary (high quality by default)

---

## 5. Common Failure Modes

### Over-specification issues:
- **Quality tag stacking** — Multiple superlatives ("hyper detailed, insanely detailed, ultra realistic") show severe diminishing returns
- **Contradictory parameters** — "Shallow depth of field" + "everything in focus"
- **Numerical precision theater** — "f/2.8, ISO 400, 1/125s" not physically simulated; descriptive terms often work equally well

### Redundant descriptors:
- **Standard focal lengths** — 50mm vs. 75mm produce nearly identical outputs; only large jumps (24mm → 85mm → 200mm) create visible differences
- **Multiple resolution tags** — One is sufficient
- **Overlapping lighting terms** — "Soft lighting, ambient lighting, diffused lighting" all point to similar patterns

### Vague language traps:
- **Generic quality terms** — "Beautiful," "stunning," "amazing" have high entropy (retrieve everything)
- **Ambiguous spatial descriptors** — "Left," "right," "above," "below" (models struggle with spatial reasoning)
- **Counting requests** — Numerals have the least influence of any word type; multi-object generation is unreliable

### Model drift patterns:
- **Anatomy-specific negative prompts** — "Bad hands, extra fingers" showed zero effect in controlled testing (likely placebo)
- **"Fuji" ambiguity** — Sometimes places Mount Fuji in image rather than invoking Fujifilm aesthetics
- **Attribute leakage** — Adjectives dominate entire scene ("rusty shovel in clean shed" makes everything rusty)

---

## 6. Reusable Prompt Template

```
Subject: [Specific physical description with details]

Shot Type: [Close-up / Medium shot / Wide shot / Extreme close-up]

Camera/Lens: [85mm / 24mm / 200mm OR plain language equivalent]

Lighting: [Golden hour / Rembrandt lighting / Rim light / Studio lighting / Natural condition]

Atmosphere: [Volumetric fog / God rays / Overcast / Morning haze / Clear]

Materials: [Visible pores / Weathered stone / Brushed metal / Specific textures]

Medium: [Editorial photograph / Cinematic still / Film photography]

Aspect Ratio: [16:9 / 3:2 / 1:1]

Negative Prompt: [Low quality, blurry, distorted, oversaturated]
```

**Filled example:**
```
Subject: 40-year-old woman with salt-and-pepper hair in loose bun, wearing linen shirt

Shot Type: Medium shot

Camera/Lens: 85mm lens, shallow depth of field

Lighting: Soft window light from left, Rembrandt lighting

Atmosphere: Slight haze, warm interior

Materials: Visible skin texture, fine wrinkles around eyes, natural catchlight

Medium: Editorial photograph, Kodak Portra 400

Aspect Ratio: 3:2

Negative Prompt: Low quality, blurry, oversaturated, artificial skin smoothing
```

**Compact version (single-line):**
```
40-year-old woman with salt-and-pepper hair in loose bun wearing linen shirt, medium shot, 85mm lens, soft window light from left, Rembrandt lighting, slight haze, visible skin texture, editorial photograph, Kodak Portra 400, 3:2
```

---

**Key takeaway:** The most effective approach is not memorizing parameter lists but understanding which categories carry signal (lighting, framing, medium, atmosphere) and which are largely noise (resolution tags, quality stacks, exact f-stops), then investing prompt tokens accordingly.
