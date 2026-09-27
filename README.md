# Visual Question Answering for Accessibility

## Team Members
- [Dana Bolden]

## Project Tier
Tier 2: This project combines two AI components, computer vision and natural language processing (a Vision-Language Model), working together to answer questions about images.

## Problem Statement
People with visual impairments or individuals navigating complex visual data often need specific details about an image that standard alt-text doesn't provide. Standard captioning is passive, but users need an active way to ask targeted questions about their visual environment.

## Solution Overview
An interactive application where a user uploads an image and types a question in plain English. The Vision-Language Model processes both inputs and outputs a natural language answer describing the specific requested details. (Flow: Image + Text Question → VLM → Text Answer).

## Technical Approach
- **CV Technique:** Visual Question Answering (VQA) / Vision-Language Model
- **Model Architecture:** Vision Transformer (ViT) combined with a language model
- **Model:** BLIP (Bootstrapping Language-Image Pre-training)
- **How we will use it:** Pretrained as-is via Hugging Face Transformers API (free open-source inference)
- **Framework:** PyTorch / Hugging Face
- **Why this approach:** BLIP provides excellent zero-shot VQA capabilities without needing expensive compute to fine-tune, allowing it to run smoothly on Google Colab's free tier.

## Dataset
- **Source:** Self-collected testing set (everyday scenes, signage, and objects) + a subset of the public VQA v2 dataset for baseline testing.
- **Size:** 50-100 images
- **Labels:** Manual question-and-answer pairs for evaluation
- **Link:** N/A (Local evaluation set)

## Success Metrics
- **Primary:** Answer Relevance/Accuracy — we will manually evaluate 100 test images and expect at least 80% of the answers to be factually correct and relevant to the question.
- **Secondary:** Inference Speed — expect the model to generate an answer in under 2 seconds per image on Colab free tier.

## Milestone Plan
| Phase | Your goal | Milestone | 16 week term |
|---|---|---|---|
| 🧭 Blueprint | Plan approved | Midterm submitted | Week 10 |
| 🔌 First Working Demo | A pretrained model runs end to end on a few sample images | Something works, even if rough | Week 11 |
| 🛠 Make It Yours | Add your data and application logic | System works on YOUR problem | Weeks 12 to 13 |
| 📈 Improve and Measure | Test, fix, and measure against your success metrics | Metrics recorded | Week 14 |
| 🎥 Package and Present | Demo video, README, final slides | Final submitted | Week 15 |

## Resources
- **Compute:** Google Colab (Free Tier)
- **Cost:** $0 (Hugging Face open-source model)

## Risks and Mitigation
| Risk | Probability | Plan B |
|---|---|---|
| Model hallucinates or gives generic answers | Medium | Adjust prompt phrasing or switch to a different lightweight model like ViLT. |
| Out of memory (OOM) errors on Colab | Low | Use the base BLIP model (`Salesforce/blip-vqa-base`) instead of the large version, and process images one at a time. |

## Current Status
- [x] Repository created
- [x] Proposal submitted
- [ ] First working demo
- [ ] System works on our data
- [ ] Metrics measured
- [ ] Final submitted
