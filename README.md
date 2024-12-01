RE_FullCode
Contains 25 code cells that focus on tasks such as data processing, model training, or visualization.
Includes 22 markdown cells, providing context, explanations, or instructions.
Purpose: Contains model fine-tuning code for the "gemma_instruct_2b_en" architecture utilizing a real estate inquiry dataset.

RE_DemoCode
Contains 11 code cells that focus on tasks such as data processing, model training, or visualization.
Includes 5 markdown cells, providing context, explanations, or instructions.
Purpose: Loads the fine-tuned model and presents a chatbot demo interface.


# Real Estate Code

This repository contains a Jupyter Notebook demonstrating the **Real Estate** model, based on the Gemma2b architecture with 2 billion parameters. The code is designed to be run on **Google Cloud Platform (GCP)** using **Vertex AI Workbench**.

## Development Environment

The code was developed on a **GCP Vertex AI Workbench** instance with the following configuration:

- **Machine Type:** Custom instance with 32GB RAM.
- **GPU:** 1 NVIDIA T4 GPU.
- **Disk:** 200GB for data storage, 150GB boot disk for the operating system and libraries.
- **Environment:** Python 3.8 JupyterLab with the required libraries installed.

This setup ensures sufficient computational resources for running large-scale machine learning tasks, including handling the Real Estate model's training and inference.

## Prerequisites

Before running the notebook on GCP, ensure the following:

1. **GCP Project Setup**
   - You have an active Google Cloud Project.
   - Billing is enabled for the project.
   - You have sufficient credits or budget to run the notebook.

2. **Google Cloud Storage (GCS) Bucket**
   - Create a GCS bucket and upload any required datasets or files referenced in the notebook.

3. **Vertex AI Workbench**
   - Enable the **Vertex AI Workbench API** in your GCP project.
   - Launch a JupyterLab environment using **Vertex AI Workbench** with a machine configuration similar to the development environment:
     - **GPU:** NVIDIA T4 or higher (for accelerated processing).
     - **RAM:** At least 32GB.
     - **Disk:** 200GB data disk and a 150GB boot disk.

4. **Install Required Libraries**
   - Open a terminal in the Vertex AI Workbench environment and run:
     ```bash
     pip install -r requirements.txt
     ```
     *(If `requirements.txt` is not available, manually install the libraries mentioned in the `import` statements in the notebook.)*

## Steps to Run the Notebook

1. **Clone the Repository**  
   Open the terminal in the Vertex AI Workbench environment and run:
   ```bash
   git clone <repository_link>
   cd <repository_folder>
   ```

2. **Upload Necessary Files**  
   Ensure any datasets or files required by the notebook are uploaded to your GCS bucket and update the file paths in the notebook to reference the bucket (e.g., `gs://<bucket-name>/<file-name>`).

3. **Open the Notebook**  
   - Launch JupyterLab from the Vertex AI Workbench instance.
   - Open `RealEstateCode.ipynb` in the Jupyter interface.

4. **Run the Notebook**  
   - Click **Cell** in the top menu.
   - Select **Run All** to execute all cells, or run cells one by one by selecting a cell and clicking the **Run** button (▶️) in the toolbar.

   **Important:** Run the cells in order if you execute them individually, as some cells depend on earlier outputs.

## Notes

- **Authentication:**  
  Ensure your notebook is authenticated to access GCP resources. Run the following in the notebook before accessing GCS or AI services:
  ```python
  from google.colab import auth
  auth.authenticate_user()
  ```

- **Resource Management:**  
  - Monitor usage to avoid unexpected costs.
  - Shut down the Vertex AI Workbench instance when not in use to save credits.

- **Error Handling:**  
  - If you encounter errors, check:
    - File paths are correct and accessible in GCS.
    - Required libraries are installed.
    - You have sufficient permissions for GCP resources.
