# 📸 Kuku FM Thumbnail Generation — Team Noobs

Welcome to the official repository submission by **Team Noobs** for the **Kuku FM Thumbnail Generation Problem**.

## 🚀 Project Overview

This project presents a robust and automated pipeline for generating high-quality thumbnails using a combination of state-of-the-art AI tools:

- **Stable Diffusion 3.5** for image generation  
- **OpenAI GPT (via API)** for prompt generation and refinement  
- **ImageReward** for image quality evaluation and ranking

Our goal is to generate visually compelling thumbnails that are not only stylistically diverse but also highly relevant to the given context.

---

## 🧠 Key Idea

The pipeline follows these major steps:

1. **Prompt Generation (GPT API)**  
   Using OpenAI's GPT model, we generate **multiple variations** of prompts from a base concept. These prompts differ in:
   - Style
   - Coherence
   - Color palette
   - Artistic tone

2. **Image Generation (Stable Diffusion 3.5)**  
   Each prompt is fed into Stable Diffusion to generate **multiple thumbnail candidates** per prompt.

3. **Image Ranking (ImageReward)**  
   All generated images are ranked using **ImageReward**, a model that scores images based on visual appeal and prompt alignment.  
   The **top-ranked image** is selected for the next stage.

4. **Prompt Refinement (GPT API Feedback Loop)**  
   The selected image is passed back into GPT via the OpenAI API to evaluate **inconsistencies or missing elements** in relation to the prompt.  
   GPT suggests improvements or final touches, which are used to **regenerate a refined prompt** for an even better result.

---

## 🛠️ Tech Stack

- 🧠 **OpenAI GPT API** — for intelligent prompt crafting and feedback
- 🎨 **Stable Diffusion 3.5** — for generating high-quality, diverse images
- 📊 **ImageReward** — for evaluating and ranking image quality
- 🐍 **Python** — glue code and orchestration logic

---

## ✅ Features

- Multi-step image generation with **style diversity**
- Automated **prompt quality control**
- GPT-powered **semantic feedback loop**
- Visual quality ranking via **ImageReward**
- Extensible and modular pipeline

---

## 📈 Future Work

- Fine-tune the prompt-to-image pipeline based on specific content types (e.g., audiobooks, genres)
- Add support for A/B testing of thumbnails
- Integrate real-time feedback from Kuku FM content teams

---

## 📬 Contact

For queries or collaboration, reach out to **Team Noobs**  
We're happy to share insights and explore improvements together!
