# Bare Prompt Output: AI Response to "Design a 15-minute simulation for design students to learn about 3D printing and CAD"

**Prompt used:** *"Design a 15-minute simulation for design students to learn about 3D printing and CAD. It should run in a browser with teams of 3-5 people."*

**Model:** DeepSeek V4 Pro (via OpenRouter)
**Date:** 2026-08-04

---

## Model Output: "PrintWorks"

### Overview

PrintWorks is a collaborative browser simulation where teams of 3–5 design students race to prototype a simple product using a constrained in-browser 3D modeling environment and a simulated 3D printer. Teams experience the full workflow — ideation, CAD modeling with real constraints (overhangs, support material, layer adhesion) — and see their designs "printed" with simulated fidelity.

### Learning Objectives

By the end of this 15-minute simulation, students should be able to:
1. Identify design features that cause common 3D printing failures (overhangs >45°, unsupported bridges, thin walls <1mm)
2. Apply basic CAD modifications (adding chamfers, fillets, support blockers) to fix printability issues
3. Evaluate print orientation tradeoffs between surface quality, strength, and material usage
4. Collaborate under time pressure to make design-for-manufacturing decisions

### Simulation Structure (15 Minutes)

**Phase 1 — Design Brief & Role Assignment (2 min)**
Teams receive a design brief: "A client needs a custom phone stand that prints in under 30 minutes on a standard FDM printer. The base model is provided but has deliberate printability issues." Team roles: Designer (modifies geometry), Print Engineer (checks printability), Project Lead (manages time and final approval).

**Phase 2 — Collaborative CAD (8 min)**
Browser-based simplified 3D editor with:
- A pre-loaded phone stand model with intentional flaws (unsupported 60° overhang, 0.6mm thin wall section, a bridge without support)
- Slider controls for: wall thickness (0.4mm–3mm), chamfer/fillet radius, support enabler toggles
- Real-time "printability heatmap" overlay showing problem areas in red/yellow/green
- Each role has different controls visible — Designer sees geometry tools, Print Engineer sees the heatmap and orientation widget

**Phase 3 — Print & Evaluate (3 min)**
Teams submit their modified model. The sim runs a virtual slicer showing:
- Estimated print time and material usage
- A "printability score" (0–100) based on overhang angles, wall thickness, bridge distances
- A simulated layer-by-layer print preview (time-lapse animation)
- Comparison dashboard showing all teams' scores

**Phase 4 — Debrief (2 min)**
Instructor leads discussion on which changes had the biggest impact on printability. Teams share one thing they would do differently.

### Browser-Based Tools
- WebGL-based simplified 3D model viewer with orbit/pan/zoom
- Constraint-based CAD editor (sliders, not freeform modeling)
- Virtual slicer engine (client-side, simplified G-code visualization)
- Collaborative state sync (WebRTC or WebSocket)
- Printability analysis algorithm (angle detection, wall thickness measurement, bridge detection)

---

## Additional Evidence: Two Independent Subagent Runs

**Both subagents used DeepSeek V4 Pro (via OpenRouter) — the same model.** Each was given the identical bare prompt. Neither was constrained to text output. Both independently produced the same pattern.

### Run 1: "PrintCraft" (deleg_4057546b)
- Built a complete interactive HTML prototype at `~/3d-printing-cad-simulation.html`
- 4 phases, 4 design challenges, 5 parametric CAD sliders, 5 slicing parameters
- 3 team roles, quality scoring with weighted dimensions
- The model autonomously loaded a design skill and chose to *build* rather than *design*

### Run 2: "PrintWorks" (deleg_09367fe1)
- Produced a written design with: **5 learning objectives**, 4 phases, **5 team roles** (Modeler, Slicer, Quality Inspector, Cost Tracker, Project Lead)
- Multiple independent controls: Layer Height (0.1–0.3mm), Infill (5%–40%), Wall Count (1–3), Support toggle
- Scoring system: Printability, Client fit, Efficiency, Quality
- Full technical architecture: Three.js, CSG engine (WASM), WebSocket sync, slicing engine, deterministic physics, instructor dashboard
- Post-sim debrief: *"What would you change if you had 5 more minutes?"* (a reflection question, not a consequential choice)

### What This Proves

The raw model output, in two independent runs, produced multi-phase, multi-objective, multi-control designs with scoring systems, role specialization, and instructor dashboards. **Neither produced a sim with one decision, one thing to learn, and three endings.** This is not a prompt-engineering failure — it is a design-philosophy gap. The model defaults to breadth over depth, features over focus, scoring over judgment.

The human contribution — constraining to one geometric parameter, one wrong surface, and three endings — is what makes a sim teachable. The model can build the tool; it cannot see which part of the tool is the teachable moment.
