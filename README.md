# The Heavy Lifting Prototype (V6.6)
### *A Hybrid Vision-to-Prompt Architecture for Mobile-Edge Computing*

## 🛠 Project Overview
**The Heavy Lifting** is an experimental framework designed to bridge the gap between local mobile-edge inference and high-fidelity cloud-based image generation. By utilizing a **Hybrid Engine** architecture, this project optimizes the workflow from image analysis (Vision-to-Prompt) to final artistic output.

The core objective is to achieve professional-grade image synthesis using a mobile-first environment (**Termux on Android**) while maintaining strict control over anatomical symmetry and texture fidelity.

## 🚀 Engine Architecture
The system operates on a **Multi-Core Flux Engine** that routes tasks based on the required "Density" of the output:

1.  **NATIVE CORE (Eco):** Powered by local **Flux.1-schnell** (4 Steps). Used for zero-cost structural anchoring and rapid layout drafting.
2.  **TURBO CORE (Hybrid):** Powered by **fal.ai (flux-lora)**. Balances generation speed with anatomical density for refined iterations.
3.  **DEV CORE (HQ):** Powered by **fal.ai (flux-lora)** at high step counts (30+). Dedicated to maximum texture fidelity and subsurface scattering.

## 🧠 The Moondream Bridge
A key feature of this research is the integration of the **Moondream Vision API** running via `llama.cpp` in a local Termux environment.
* **Objective Reality Analysis:** Translates source images into pure, style-neutral text descriptions.
* **Immutable Geometry:** Ensures structural integrity (camera angles, focal length, and pose) remains constant during the "Style Injection" phase.

## 📋 Prompt Hierarchy Protocol
All generations follow a standardized logical hierarchy to ensure consistency across different model scales:
* **Master Sequence:** Medium & Style ➔ Camera Framing ➔ Core Subject ➔ Specific Features ➔ Pose ➔ Clothing ➔ Environment ➔ Lighting.
* **Anatomical Hardcode:** Every request triggers a specific geometry constraint for flawless skeletal alignment and distinct limb separation.

## 📦 Technical Stack
* **Environment:** Termux (Android/Linux)
* **Inference Engine:** Llama.cpp (Local) / fal.ai API (Cloud)
* **Vision Model:** Moondream2
* **Generation Models:** Flux.1-schnell & Flux.1-dev
