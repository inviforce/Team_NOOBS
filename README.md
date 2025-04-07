# ThumbnailGen: AI‑Driven Podcast Thumbnail Generation

**Project:** KukuFM Hackathon  
**Team:** Your Team Name  
**Date:** YYYY‑MM‑DD  

---

## 🚀 Overview

**ThumbnailGen** is an end‑to‑end pipeline that transforms podcast episode keynotes into eye‑catching thumbnails using:

1. **GPT‑4O** for prompt engineering  
2. **Stable Diffusion 3.5 Large** for high‑quality image generation  
3. **Image Reward** for ranking images

---

## 📦 Features

- **Automated Prompt Generation**  
  - Generates 5 positive & 5 negative prompts under token limits  
  - Ensures title is integrated into each positive prompt

- **Image Quality Ranking**  
  - Uses **ImageReward** model to rank multiple generated thumbnails  
  - Automatically selects the top‑scoring image for use
  
- **High‑Resolution Thumbnails**  
  - Uses SD3.5 to produce 512×512 images with 8K‑style detail  
  - Configurable inference steps & guidance scale  

- **Fallback & Robustness**  
  - Gracefully falls back to original keynotes if prompt regeneration fails  
  - Supports gated & public Stable Diffusion models  

---

## ⚙️ Setup

1. **Clone Repo**  
   ```bash
   git clone https://github.com/your‑org/thumbnailgen.git
   cd thumbnailgen
   ```
2. **Install dependencies**  
   ```bash
    pip install \
        diffusers transformers accelerate safetensors \
        pillow huggingface_hub openai\
        image-reward

   ```
3. **Authenticate**  
   ```bash
   git clone https://github.com/your‑org/thumbnailgen.git
   cd thumbnailgen
   ```
    ### Huggingface
    from huggingface_hub import notebook_login
    notebook_login()

    ### OpenAI
    export OPENAI_API_KEY="sk‑..."

## 📝 Usage

### Prepare Keynotes

Create a list of tuples:

```python
    container = [
    ("Episode keynote text…", "/path/to/cover.jpg", "Episode Title"),
    # …
    ]
```

### Regenrate prompts

```python
    positives, negatives = gpt_generating_prompts(base_prompt, image_title)
```


### Generate Thumbnails

```python
    img = generate_thumbnail(
    prompt=positives[0],
    neg_prompt=negatives[0],
    title=image_title,
    steps=25
    )
    img.save("thumbnail.png")

```

### Batch Processing

```python
    for keynote, img_path, title in container:
    try:
        pos, neg = regenerate_prompt(img_path, keynote)
        if not pos:
            raise ValueError
    except:
        pos, neg = [keynote], [""]
    thumb = generate_thumbnail(pos[0], neg[0], title)
    thumb.save(f"{title}_thumb.png")


```

## 📂 Notebook

See **`ThumbnailGen_Notebook.ipynb`** for a runnable Google Colab notebook with full code, examples, and a visual gallery.

---

## 🎨 Examples

| Keynote Excerpt                                 | Generated Thumbnail Preview         |
|-------------------------------------------------|-------------------------------------|
| “In the dark underbelly of New York City…”      | ![preview1](examples/previ ew1.png)  |
| “A tale of power, betrayal, and redemption…”    | ![preview2](examples/preview2.png)  |

---

## 🔮 Future Work

- Batch & Parallel Processing  
- Interactive UI / Web App  
- A/B Testing & Analytics  
- Support for Additional Styles & Aspect Ratios  

---

## 🤝 Contributing

1. Fork this repo  
2. Create your feature branch  
   ```bash
   git checkout -b feat/YourFeature
