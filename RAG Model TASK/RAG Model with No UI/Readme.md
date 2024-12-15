# RAG_Model_with_No_UI

This notebook demonstrates how to run a Retrieval-Augmented Generation (RAG) model with no user interface (UI) in Google Colab using PyTorch, Hugging Face models, and document retrieval techniques. Below are the steps to get started.

Created by **Pranjal Kumar Sinha**.

## Requirements
- Google Colab account
- Hugging Face account with access to the **google/gemma-1.1-7b-it** model
- PDF files to be uploaded for document processing

## How to Run

### 1. Open the Notebook in Google Colab
- Open the provided `.ipynb` file in [Google Colab](https://colab.research.google.com/).
- Go to **File** > **Open Notebook**, then select the file from Google Drive or upload it directly.

### 2. Set the Runtime to T4 GPU
- Go to **Runtime** > **Change runtime type**.
- Set **Hardware accelerator** to **GPU** (T4 is recommended).
- Click **Save**.

### 3. Install Required Libraries
- First, ensure that you run all cells that contain the following `pip install` commands. These will install necessary libraries like `PyTorch`, `Hugging Face Transformers`, `LangChain`, `FAISS`, `pdfplumber`, and others:
  
### 4. Prepare the Document Folder and Upload PDFs
- Create a folder named **documents** in Colab:
- Upload the PDF manual into the `/content/documents` folder.

### 5. Fetch the Documents
- In the notebook, there's a cell where the folder path is defined for loading PDFs. After uploading the PDFs, modify the folder path accordingly:
  ```python
  folder_path = r'/content/documents'
  ```

- Once the path is set, run the cell that fetches and converts the PDF files into text files for processing.

### 6. Obtain Hugging Face Access Token
- Visit the [google/gemma-1.1-7b-it](https://huggingface.co/google/gemma-1.1-7b-it) model page.
- Log in or sign up to Hugging Face if you haven’t already.
- Request access to the model and generate an **access token** from Hugging Face.
  - Go to **Settings** > **Access Tokens** > **Create New Token**.
  - Ensure the following two permissions are enabled for the token:
    - **Read access to contents of all repos under your personal namespace**
    - **Read access to contents of all public gated repos you can access**

- Copy the token and paste it in the appropriate cell in the notebook:
  ```python
  login(token="your_hugging_face_token_here")
  ```

### 7. Run All Remaining Cells
- After the access token is added, run the remaining cells to set up the model, query documents, and generate responses.
- The main query to be executed is:
  ```python
  query = "How to make a SOS call?"
  ```

### 8. Review the Output
- The output will include relevant documents retrieved from the uploaded PDFs, followed by a generated response.
