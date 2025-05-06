# Image-Generation
# Generative AI Lab: Text-to-Image Product Visualization

This repository contains the code, data, and prompt outputs from our project for **94-844: Generative AI Lab** at Carnegie Mellon University.

## 📌 Project Overview

This project explores how customer reviews can be translated into realistic product images using **text-to-image generation models**. We developed a Retrieval-Augmented Generation (RAG) pipeline that takes in Amazon product reviews and descriptions and outputs prompts used to generate images using **DALL·E 3** and **Stable Diffusion 3.5 Large**.

We selected three distinct products:
- ☕ **Breville Espresso Machine** (Home & Kitchen)
- 🎮 **Meta Quest 3 VR Headset** (Electronics)
- 🥁 **Handpan Drum** (Musical Instruments)

These represent high, medium, and low-revenue Amazon categories, allowing us to test across varying levels of data availability and product familiarity.

## 💡 Methodology

### 1. **Document Processing and Embedding**
- **Tools:** `PyMuPDF`, `llama_index`, OpenAI `text-embedding-ada-002`, Pinecone
- Paragraph chunking with keyword and summary extraction
- Embeddings stored in Pinecone using cosine similarity

### 2. **Prompt Engineering with GPT-4**
- Prompts designed for **image generation** with visual and functional product features
- Focused on *authenticity*, *usability*, and *balanced representation* using user reviews
- Incorporated review sentiment and feedback

### 3. **Image Generation**
- Used **DALL·E 3** for artistic and creative interpretations
- Used **Stable Diffusion 3.5 Large** for realistic, product-matching visuals
- Prompts adapted for 77-token limit in Stable Diffusion

### 4. **Prompt Refinement Steps**
- Base summary → “make it visual” → added user reviews → context of helping a 3D artist
- Final prompts emphasize specificity, visual clarity, and realism

## 🧪 Key Experiments

| Experiment                           | DALL·E 3                            | Stable Diffusion 3.5               |
|-------------------------------------|------------------------------------|-----------------------------------|
| **Breville Machine**                | Visually appealing but stylized    | Accurate but less visually rich   |
| **Meta Quest 3**                    | Emphasized futuristic design       | Captured realistic proportions    |
| **Handpan Drum**                    | Artistic textures & colors         | Better product fidelity           |

## 🔧 Tools & Libraries Used

- `OpenAI GPT-4`, `text-embedding-ada-002`
- `Pinecone`
- `llama_index`, `PyMuPDF`
- `Stable Diffusion 3.5 Large`
- `DALL·E 3`

## 📁 Folder Structure

```
├── RAG/                   # Storing product descriptions in a vector store
├── Image Generation/                # Final prompts used for image generation
├── product_info_pdf.pdf/                # Reviews and information about the products scraped from the internet
├── Report.pdf/                # Final report
```

## 📊 Results Summary

- DALL·E 3 produced **aesthetic and creative visuals**, ideal for marketing
- Stable Diffusion generated **accurate product renditions**, ideal for e-commerce
- Iterative prompt design significantly improved visual fidelity
- Combining **positive and negative reviews** provided balanced and trustworthy outputs

## 📚 References

- [Stable Diffusion 3.5 Large – Hugging Face](https://huggingface.co/stabilityai/stable-diffusion-3.5-large)
- [Top Amazon Product Categories](https://www.junglescout.com/resources/articles/amazon-product-categories/)

## 📎 Authors

Ashwin Kandath, Hoklam Cheung, Praneet Yavagal, Rahul Pujari, Yukti Shah  
Carnegie Mellon University  
Course: 94-844 Generative AI Lab

---

## ✅ Run Instructions

To run the code in this folder, make sure to install the requirements:

```bash
pip install -r requirements.txt
```