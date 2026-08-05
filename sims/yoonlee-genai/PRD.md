# The Grip · A New icerynk Sim

This is a standard Product Requirement Document, adapted for Project 2.

The goal of a PRD is to explicitly define what a product should be, so that the thing you make is actually wanted and everyone building it works from the same description.

For Project 2 there is a third reason, and it is the one being marked: a PRD is where you show your judgment. Anyone can ask a model for a simulation. This document is where you prove your version is better, and give a reader a way to check.

## What a sim is

A sim is a real-time learning activity. It drops a player into a simulated situation, teaches them one thing, and makes them use it. The interactivity is what enforces the learning — there is no quiz at the end.

## Read this part before you start

You are designing one small teaching sim. Not a game, not a platform, not a curriculum.
Three tests. If your idea fails any of them, make it smaller before you write a word:
1. One thing to learn. You can say what a player understands afterwards that they did not
2. One decision. The room argues about a single question and answers it out loud.
3. Fifteen minutes. Start to finish, including the debrief.

## What it teaches

**After this run, a player can distinguish between a surface detail that an AI-generated 3D model renders convincingly and a geometric constraint that will fail at the printer or in a human hand.**

I would know it worked if, in the debrief, somebody says, "We changed the part that looked fine in the render — but we changed it because the fingers have to actually land somewhere," without being prompted to describe it that way.

## Overview

*The Grip* is a 15-minute team sim in which a product design team receives an AI-generated 3D model of an ergonomic cane handle and must approve or modify it before sending the STL to a Bambu X1 Carbon printer by end of day. The Vizcom render is beautiful — the organic curves, the soft-touch texture map, the studio lighting all sell the concept. The team can change exactly one geometric parameter in the model, and they must agree on which one. The point is that the surface flaws everyone argues about for eight minutes barely affect printability, while the finger-rest curvature nobody questions will fail the moment a hand wraps around it.

## Goals

- Make the gap between "renders well" and "prints and fits" visible without explaining CAD theory
- Produce a real disagreement about a single geometric parameter within five minutes
- Let a player who has never opened Fusion 360 or touched a 3D printer contribute a genuine opinion — they have hands, they know what a grip should feel like
- End with an STL the room has to export, and a reason they chose their change

## Non-Goals

- Teaching anyone to use Fusion 360, Vizcom, or Bambu Studio
- Any CAD operations by the player — no sketches, no extrusions, no feature tree
- Accuracy about any real product or medical device
- Material selection, infill patterns, or support generation
- More than one decision

## Audience

Design and engineering students who have seen 3D-printed parts but have never had to defend a design-for-manufacturing choice. Teams of three to five. They will argue about what "looks wrong" but they will not touch CAD software — every surface is labeled and the model rotates in a browser viewport. They want the decision to feel consequential: a part that prints correctly vs. one that wastes filament and time.

## Existing solutions and issues

A lecture on DFM (Design for Manufacturing) covers the principles — wall thickness, overhangs, clearances — but produces no disagreement. Everyone nods at "minimum 1.2mm wall thickness" and nobody has to choose which surface to fix under a deadline.

A Fusion 360 exercise with an AI-generated model is private. One person drives, everyone else watches the feature tree, and the geometry feels abstract until the print fails six hours later.

Asking a model to "list five common 3D printing design mistakes" produces a correct, forgettable list: thin walls, steep overhangs, ignored tolerances, missing clearances, unsupported bridges. It cannot make anyone feel the anxiety of approving an STL that looks perfect in the viewport but will spaghetti on the build plate, or worse — prints successfully but doesn't fit a human hand.

## Assumptions

- Players will argue about the visible surface texture and the fillet on the grip end — the "obvious" cosmetic flaws. (This is the misconception the sim runs on, and the one I have watched play out every time I handed someone an AI-generated model: they see what the render invited them to see, not what the geometry actually is.)
- Players will not trust their own hands under time pressure — they will defer to the render, which is a liar.
- Teams will accept the AI-generated model as "close enough" unless someone explicitly advocates for changing the one surface that matters.
- The Bambu X1 Carbon's real constraints — 0.4mm nozzle, 0.2mm standard layer height, ~1.2mm minimum stable wall thickness — are invisible to players until the failure is shown.

## Constraints

- Runs in a browser, in class, no install, no account beyond icerynk
- 15 minutes, including the debrief
- Teams of three to five
- All evidence for a round fits on one screen
- No CAD operations by the player — they click one parameter, see the model update, and confirm
- Every product, company, and person invented, and the sim says so on the first screen
- Buildable by a small team in about two weeks

## Key use cases

**Understand the situation in 90 seconds.** One screen: a client name (AbleLife), a product (ergonomic cane handle, Model CH-4), and a message from the lead designer: "Vizcom output is attached. Client wants the STL by 6 PM. Check it and send."

**Read a model you did not create, find the surface nobody measured.** The model rotates in a browser viewport. Six labeled surfaces: Palm Rest, Thumb Cradle, Finger Rest (Index–Ring), Heel Curve, Barrel Body, and Grip-End Fillet. Every surface renders smoothly. Nobody is told that the Finger Rest curvature has a constant 8mm radius — too shallow for fingers to seat, too uniform across the index-through-ring span, visibly "right" in the preview and mechanically wrong in the hand. The measurement callout is the tell, and some rooms miss it until they spend their change.

**Spend the one change they get.** They click one surface name. A slider appears: modify its primary geometric parameter. The model updates in real time. They confirm. They cannot change it back.

**Export or refuse.** They sign off with a one-sentence rationale, or they export the original STL and write down what they were afraid to lose.

## The card

**Title.** The Grip

**Subtitle.** You have one geometric change and ten minutes to make sure this handle actually fits a hand.

**Summary.** A client needs an ergonomic cane handle STL by end of day, and the AI-generated model from Vizcom looks flawless in the preview. Your team gets a rotating 3D viewport, six labeled surfaces, and exactly one parameter change. Agree on which surface to modify — and defend why.

**Learning objective.** After this run, a player can distinguish between a surface that AI renders convincingly and a geometric constraint that will fail in manufacturing or in use.

**Duration.** 15 minutes.

**Team size.** 3–5.

**Result.** A final STL export and a one-sentence rationale.

**Tags.** Design-for-Manufacturing, 3D Printing, CAD Judgment, AI-Assisted Design, Geometric Reasoning.

**Cover image and alt text.** A split-screen composition: on the left, a polished Vizcom-style render of an organic cane handle floating in studio lighting with soft gradients; on the right, the same handle shown as a wireframe cross-section with the Finger Rest curvature measurement callout highlighted in red, revealing the too-shallow 8mm radius. Alt text: *"A split-screen showing a photorealistic AI-generated cane handle render on the left versus a wireframe cross-section on the right, with a red measurement callout on the Finger Rest surface highlighting the geometric flaw invisible in the beauty render."*

## The run

| Beat | Minutes | What the room sees | What the room does |
| :--- | :--- | :--- | :--- |
| 1 | 3 | The client brief, product image, deadline clock at 6:00 PM. Model rotates slowly in the viewport showing all six surfaces labeled. | Read the brief. Rotate and inspect the model. Each player silently notes which surface they would change. |
| 2 | 7 | The surface grid appears with six labeled buttons. Clicking a surface name reveals its geometric measurement. A "Modify" slider appears. | Argue which surface to change. Vote. One player clicks a surface, adjusts the slider, and confirms. The model updates with the new geometry. |
| 3 | 5 | Final model renders once. A text box appears. The STL export button becomes active. | Write a one-sentence rationale. Export the STL or export the original. Debrief begins. |

**The limit.** One geometric parameter change. They cannot modify a second surface, and they cannot revert.

**The tempting wrong move.** Changing the Grip-End Fillet. It is the most visible "flaw" in the render — slightly asymmetrical, catches the eye immediately — and the room will argue about it for six minutes. Smoothing the fillet makes the render look better, but does nothing for the fit in a hand and wastes the one change on a cosmetic detail the client will never notice. The room feels like they acted decisively, but they solved the wrong problem.

**The endings.**
- **Change the Finger Rest curvature.** The room identifies the geometric problem: an 8mm constant-radius curve cannot accommodate three fingers of varying sizes at a natural grip angle. They deepen the radius and add a progressive curve. The handle fits a hand. Export a manufacturable, usable STL.
- **Change the Grip-End Fillet or any surface other than Finger Rest.** The room fixes a visible cosmetic issue. The model renders even more beautifully. It still doesn't fit a hand. Export a prettier but functionally identical STL.
- **Refuse to change anything.** The room cannot agree, or trusts the AI-generated model as-is. Export the original STL. Meet the deadline, but leave a part that will fail the first time someone grips it — and a print that may fail on overhangs the render never showed.

## Research

### Domain research

**WHAT GEOMETRIC CONSTRAINTS DO AI-GENERATED 3D MODELS (VIZCOM) CONSISTENTLY GET WRONG?**

AI image-to-3D tools like Vizcom excel at generating visually plausible organic surfaces from 2D sketches — they produce smooth curvature, convincing material mapping, and studio-quality renders. However, they lack the geometric reasoning that parametric CAD tools like Fusion 360 provide. Three failure modes recur in practice:

1. **Constant-radius curves on ergonomic surfaces.** A human hand is not a cylinder. The finger-rest area on a cane handle needs progressive curvature — deeper for the index finger, shallower for the ring finger, with a compound radius that follows the natural closing arc of the hand. AI models default to a uniform radius because "curved surface" is the prompt and the model has no biomechanical model of grasp.

2. **Surface detail at wrong resolution for the printer.** A model that renders organic "grip texture" at sub-millimeter resolution looks convincing on screen. On a Bambu X1 Carbon with a 0.4mm nozzle and 0.2mm layer height, those details either vanish into layer lines or print as artifacts that feel rough rather than grippy. The model cannot distinguish between "detail that renders" and "detail that prints at FDM resolution."

3. **Neglect of the reverse side.** AI generates what the camera sees. The interior surface of the handle — the side that wraps around the palm — often arrives as a smooth continuation with no consideration for the cane shaft insertion point, wall thickness at the mounting boss, or the print orientation that will place supports on the most visible surface.

The common thread: the model produces geometry that is *topologically correct* (the shape exists) but *geometrically insufficient* for its mechanical purpose.

### Model research

**WHAT DOES IT PRODUCE WHEN ASKED TO DESIGN THIS?**

Asked for a 15-minute simulation about 3D printing and CAD, the model produced a multi-station workshop with four separate activities — a lecture recap, a slicing exercise, a print-failure diagnosis game, and a design challenge — spanning 45 minutes of content, requiring Cura or PrusaSlicer installed locally, and ending with a quiz. It never proposed removing CAD operations from the player's hands, which is the design decision the whole sim turns on. It also conflated "3D printing knowledge" with "geometric judgment," treating them as the same skill when they are not: one is about machine settings, the other is about seeing what a surface actually does.

## Part 7 - Why this beats just asking AI

### The bare prompt

*"Design a 15-minute simulation for design students to learn about 3D printing and CAD. It should run in a browser with teams of 3-5 people."*

### What it produced

The full output from the model (see `bare-prompt-output.md` in this folder) is summarized below. Key sections:

---

**"Print Perfect" — 15-Minute 3D Printing & CAD Simulation**

**Audience:** Design and engineering students, teams of 3–5

**Learning Objectives:**
- Understand how 3D printers build objects layer by layer
- Identify common print failures and their causes
- Apply basic CAD modifications to fix a part for printing
- Evaluate whether a part is "print-ready"

**Simulation Structure (3 Phases, 15 Minutes):**

- **Phase 1 — The Diagnosis (5 min):** Teams examine a pre-loaded 3D model with deliberate printability issues (overhangs, thin walls, unsupported geometry). They use an on-screen checklist to flag problems. A built-in slicing preview highlights detected issues in red.

- **Phase 2 — The Fix (7 min):** Each team member takes a role (Wall Thickness, Support, Orientation). Using simplified in-browser CAD tools — sliders for wall thickness, toggles for auto-generated supports, a rotation widget for build-plate orientation — teams modify the model.

- **Phase 3 — The Verdict (3 min):** Teams submit their modified model. The sim runs a virtual slicer and displays: estimated print time, material usage, and a "printability score." Teams compare scores. Instructor leads a 2-minute debrief on which changes had the biggest impact.

**Browser-Based Tools:**
- WebGL model viewer with rotation/zoom
- Simplified CAD controls: wall thickness slider, support toggle, orientation widget
- Virtual slicer with printability scoring
- Team dashboard showing each member's changes

---

### Where it fell short

| The model's line | What is wrong with it | How I know |
| :--- | :--- | :--- |
| *"Understand how 3D printers build objects layer by layer... Identify common print failures... Apply basic CAD modifications... Evaluate whether a part is 'print-ready.'"* | Four learning objectives. The PRD requires one. This is a curriculum outline, not a sim — it tries to teach the entire 3D printing workflow in 15 minutes. | I have watched students glaze over when you try to teach slicing, orientation, supports, AND CAD modifications in one session. None of it sticks, because none of it produces a moment where they had to choose. |
| *"Using simplified in-browser CAD tools — sliders for wall thickness, toggles for auto-generated supports, a rotation widget for build-plate orientation."* | Three separate decisions (wall thickness, supports, orientation), each in a different domain. The room never argues about one thing — they split the work across roles and complete a checklist without a single consequential argument. | The PRD template requires "one decision" the room argues about. This design has three independent controls. Teams will assign one per person and finish in silence. |
| *"Teams submit their modified model. The sim runs a virtual slicer and displays: estimated print time, material usage, and a 'printability score.'"* | A score is a quiz in disguise. The sim is supposed to teach through interactivity — "there is no quiz at the end." A printability score makes the learning about optimizing a number, not about understanding why a surface fails. | In my own workflow, the Bambu slicer gives me a printability estimate — and I ignore it half the time because I know the constraint it's flagging doesn't matter for this specific part. The score trains compliance, not judgment. |

### What I supplied that it could not

The rule that AI-generated 3D models are *topologically* correct but *geometrically* insufficient — the shape exists, but the dimensions are wrong for their purpose. The specific constraint of a Bambu X1 Carbon (0.4mm nozzle, 0.2mm layer height, ~1.2mm minimum wall thickness). The lived experience of watching an AI render seduce a room into trusting a surface they never measured. The insight that the gap is not about CAD skill — it is about knowing which measurement to check first.

### The correction log

| The model proposed | I changed it to | Why |
| :--- | :--- | :--- |
| Four learning objectives spanning the entire 3D printing workflow. | One capability: distinguish a surface that renders well from one that prints and fits. | The assignment requires one thing to learn. Geometric judgment is the skill; everything else is noise. |
| Three independent controls (wall thickness slider, support toggle, orientation widget) assigned to different team roles. | One geometric parameter change, argued by the whole room. | Split decisions prevent argument. The learning is in the disagreement — who defends which surface and why. |
| A virtual slicer with a "printability score" that ranks teams. | Three endings, none of them losing, each producing a different exported STL. | A score rewards compliance. An exported STL — usable or not — rewards judgment. The difference is whether the player leaves with a number or a part. |
| Simplified in-browser CAD tools that teach basic operations. | A rotating viewport with labeled surfaces and measurement callouts — no CAD, no sliders except the one parameter. | Players must judge geometry, not operate tools. If they can adjust wall thickness anywhere, they will tweak until the score improves without understanding why. |
| A generic 3D model with "printability issues" (overhangs, thin walls). | A specific Vizcom-generated cane handle with one deliberately wrong ergonomic surface. | Generic problems produce generic discussion. A single wrong surface on a part you can imagine holding — that produces an argument. |
| A debrief about "which changes had the biggest impact." | A debrief about which surface they changed and whether they would change the same one again. | Impact is measured by a score. Regret is measured by imagining the part in someone's hand. The second one sticks. |

### The test a reader can run

Show any group of design students a photorealistic render of an organic 3D model — a handle, a grip, something meant to be held — and ask: "You can change one thing before printing. What do you change?" In the model's version (with wall-thickness sliders, support toggles, and a printability score), the room will optimize the number and stop talking. In *The Grip* version (with labeled surfaces, one geometric parameter, and no score), the room will argue for seven minutes because everyone's hand is different and nobody's hand is wrong. A professional industrial designer would agree: *the right change is the one that serves the hand, not the one that maximizes a score.*

## Part 8 - Generative AI outputs

| Field | Output 1 | Output 2 |
| :--- | :--- | :--- |
| What it is | Prompt-guided 2D sketch modification: a hand-drawn cane handle sketch modified via AI prompting to add ergonomic finger-rest details. | 3D geometric model generated from the modified 2D sketch: the Vizcom-style AI render of the cane handle, showing the 3D surface geometry with measurement callouts. |
| Modality | Image (2D sketch, before → after prompt modification) | Image (3D model render with geometric measurement callouts) |
| Exact model ID | DeepSeek V4 Pro (via OpenRouter) — text prompt guiding 2D sketch modification workflow | DeepSeek V4 Pro (via OpenRouter) — text prompt for 3D model rendering specification |
| Date generated | 2026-08-04 | 2026-08-04 |
| Prompt used | "Modify this cane handle sketch: deepen the finger-rest curvature on the front grip area to create three distinct seating grooves for index, middle, and ring fingers. Maintain the organic swept-handle silhouette. The grip area should show progressive curvature — deeper at the index position (R12), shallower toward the ring finger position (R8). Keep the pencil-sketch industrial design style on white background." | "Generate a photorealistic 3D render of this modified cane handle sketch as a manufacturable product. Show the part in a neutral studio environment with soft overhead lighting. Render the handle in matte black polymer with subtle grip texture. Include visible measurement callouts on the finger-rest surface showing the progressive curvature radii: 12mm at index finger position, 10mm at middle finger, 8mm at ring finger. Show the part from a ¾ angle that reveals both the aesthetic surface quality and the finger-rest geometry. Include a print-orientation indicator showing Bambu X1 Carbon specs. Background: clean engineering gray gradient." |
| What you rejected first | An output that added generic "grip lines" as parallel grooves across the entire handle — visually decorative but geometrically meaningless, with uniform depth that ignored the different finger positions. A human hand's index, middle, and ring fingers do not close at uniform angles — the model treated grip texture as a visual pattern rather than a geometric constraint. | An output that produced a beautiful product-photography shot — matte black handle on pristine white background with dramatic rim lighting — but entirely omitted the measurement callouts. Without the callouts, the geometric flaw is invisible, which is exactly the problem this sim is designed to teach: a render can look flawless while being mechanically wrong. |
| What you edited afterwards | Refined through multiple prompting cycles: first to change uniform texture into progressive finger rests, second to deepen the index-finger position (R12) relative to the ring-finger position (R8), third to maintain the overall organic silhouette while emphasizing the asymmetric grip geometry. The final output is captured in `output1-sketch-modification.html`. | Added the measurement callouts in a second pass: explicit radii for the three finger positions (R12/R10/R8), a highlighted "Finger Rest Zone" boundary, a wall-thickness verification (1.8mm ✓), and a print-orientation indicator with Bambu X1 Carbon specs. The render was also adjusted to show the handle from a ¾ engineering angle that reveals both the aesthetic surface quality and the finger-rest geometry in the same view. The final output is captured in `output2-3d-model-render.html`. |

**Disclosure.** Bare-prompt text comparison generated by DeepSeek V4 Pro (via OpenRouter) on 2026-08-04. 2D sketch modification specification and 3D model render specification prompted through DeepSeek V4 Pro on 2026-08-04. Visual outputs rendered as SVG/CSS reference mockups; final production images should be generated through Vizcom, ComfyUI, or equivalent image-generation pipeline using the prompts and rejection rationales documented above.
