# Proactive Text-to-Image Agents Evaluation

This project implements and evaluates proactive multi-turn text-to-image (T2I) agents across multiple datasets. The goal is to analyze how iterative prompt refinement improves image generation quality and alignment with ground truth descriptions.

## Repository

Project Repository:  
https://github.com/Khushi191201/csci-5980-final-project

Agent Implementation (included in this repo):  
https://github.com/Khushi191201/proactive_t2i_agents

---

## Repository Structure

```
.
├── agent/                      # Core agent implementation
├── designbench/               # DesignBench dataset utilities
├── figures/                  # Supporting figures
├── DesignBench/
│   └── AISDM_PROJECT_DesignBench.ipynb   # Example notebook for DesignBench
├── coco/
│   └── AISDM_PROJECT_coco.ipynb          # Example notebook for COCO
├── agent_demo.ipynb
├── setup.py
├── LICENSE
├── CONTRIBUTING.md
└── README.md
```

All required code is included in this repository. No external cloning is required.

---

## Results

All generated outputs and evaluation results are stored here:

https://drive.google.com/drive/folders/1Viic0Q5gIPQseFeGJKIaAKRo9U-HRYOe?usp=drive_link

This includes:
- Generated images for all agents  
- Prompt logs  
- Evaluation outputs (T2T, DINO, VQAScore, NLL)  
- Comparison visualizations  

---

## Setup Instructions

### 1. Open in Google Colab

Example notebooks are provided for both datasets:
- `DesignBench/AISDM_PROJECT_DesignBench.ipynb`
- `coco/AISDM_PROJECT_coco.ipynb`

---

### 2. Clone This Repository

```
git clone https://github.com/Khushi191201/csci-5980-final-project.git
```

Then in the notebook:

```
%cd /content/csci-5980-final-project
import sys
sys.path.insert(0, "/content/csci-5980-final-project")
```

---

### 3. Configure Google Cloud

Update the project ID:

```
project = "YOUR_PROJECT_ID"
```

---

### 4. Authenticate

```
gcloud auth login
```

---

### 5. Dependencies

All dependencies are installed within the notebooks as needed.

---

## How to Run

Each notebook follows the same pipeline:

### Step 1: Dataset Preparation
- Load dataset (DesignBench or COCO)
- Construct initial prompts and ground truth captions

---

### Step 2: Image Generation
Run four agent variants:
- T2I (baseline)
- Attribute Agent (Ag1)
- Belief Agent (Ag2)
- LLM Agent (Ag3)

Each agent performs multi-turn prompt refinement.

---

### Step 3: Save Outputs
- Images saved locally and to Google Drive  
- Prompts stored for evaluation  

---

### Step 4: Evaluation

Metrics computed:
- T2T (text embedding similarity)
- DINO (image feature similarity)
- VQAScore (LLM-based alignment)
- NLL (belief state divergence)

---

### Step 5: Visualization
- Comparison grids  
- Summary tables  

---

## Reproducibility

To reproduce results:

1. Clone the repository  
2. Open notebook in Colab  
3. Set your Google Cloud project ID  
4. Run all cells sequentially  

All outputs will be generated and stored automatically.

---

## Notes

- Dataset size is limited to 30 samples for efficiency  
- Results are cached to avoid recomputation  
- Some LLM-based parsing steps may occasionally fail and are handled gracefully  

---

## Author

Khushi Kantula
