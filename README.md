# Proactive Text-to-Image Agents Evaluation

This project implements and evaluates proactive multi-turn text-to-image (T2I) agents across multiple datasets. The goal is to analyze and reproduce how iterative prompt refinement improves image generation quality and alignment with ground truth descriptions.

## Repository

Project Repository:  
https://github.com/Khushi191201/csci-5980-final-project

---

## Repository Structure

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
- DesignBench/AISDM_PROJECT_DesignBench.ipynb  
- coco/AISDM_PROJECT_coco.ipynb  

---

### 2. Clone This Repository

git clone https://github.com/Khushi191201/csci-5980-final-project.git

Then in the notebook:

%cd /content/csci-5980-final-project  
import sys  
sys.path.insert(0, "/content/csci-5980-final-project")

---

### 3. Set Up Google Cloud & Vertex AI

Follow these steps before running the notebooks:

#### a. Create a Google Cloud Project
- Go to: https://console.cloud.google.com/  
- Create a new project  
- Copy the Project ID  

#### b. Enable Required APIs
Enable the following APIs:
- Vertex AI API  
- Generative AI API  

https://console.cloud.google.com/apis/library  

#### c. Set Up Billing
- Enable billing for the project  
- Required for Vertex AI usage  

#### d. Authenticate in Colab

gcloud auth login  

#### e. Set Project ID in Notebook

project = "YOUR_PROJECT_ID"  

or  

os.environ["VERTEX_PROJECT_ID"] = "YOUR_PROJECT_ID"  

---

### 4. Dependencies

All dependencies are installed within the notebooks as needed.

---

## How to Run

Run all the cells in the notebook. Each notebook follows the same pipeline:

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


## Citation

```bibtex
@misc{hahn2024proactive,
  title={Proactive Agents for Multi-Turn Text-to-Image Generation Under Uncertainty},
  author={Hahn, Meera and Zeng, Wenjun and Kannen, Nithish and Galt, Rich and Badola, Kartikeya and Kim, Been and Wang, Zi},
  year={2024},
  eprint={2412.06771},
  archivePrefix={arXiv},
  primaryClass={cs.AI}
}