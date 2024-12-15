# RAG_final

This notebook demonstrates how to run a Retrieval-Augmented Generation (RAG) model with a user interface (UI) built using Streamlit. Below are the steps to set up and run the notebook in Google Colab.

## Requirements
- Google Colab account
- Hugging Face account with access to the **google/gemma-1.1-7b-it** model
- PDF files for document processing

## How to Run

### 1. Open the Notebook in Google Colab
- Open the provided `.ipynb` file in [Google Colab](https://colab.research.google.com/).
- Go to **File** > **Open Notebook**, then select the file from Google Drive or upload it directly.

### 2. Set the Runtime to T4 GPU
- Go to **Runtime** > **Change runtime type**.
- Set **Hardware accelerator** to **GPU** (preferably T4).
- Click **Save**.

### 3. Install Required Libraries
- Run all the cells that contain `pip install` commands to install the necessary libraries such as PyTorch, Hugging Face Transformers, FAISS, LangChain, and more:

### 4. Add Hugging Face Access Token in `RAG_App.py`
- In the `RAG_App.py` file, an access token for Hugging Face is required to use the **google/gemma-1.1-7b-it** model.
- Visit the model page at [Hugging Face](https://huggingface.co/google/gemma-1.1-7b-it).
- Log in or sign up for Hugging Face.
- Request access to the model and generate an **access token**:
  1. Go to **Settings** > **Access Tokens**.
  2. Create a new token and give it the following permissions:
     - **Read access to contents of all repos under your personal namespace**
     - **Read access to contents of all public gated repos you can access**
  3. Check the two permissions above and save the token.
  4. Copy the token and paste it into the `login(token="")` line in `RAG_App.py`.

### 5. Run the wget Command
- Run the following command to get the passcode needed for the Streamlit app:
  ```bash
  !wget -q -O - ipv4.icanhazip.com
  ```
- This command will provide you with a passcode. Save it for later use.

### 6. Run the Streamlit App
- After setting up the token, run the last cell to start the Streamlit app:
  ```bash
  !streamlit run RAG_App.py & npx localtunnel --port 8501
  ```
- It will ask you to enter **y** to provide your URL.
- Enter **y**, then click on the generated URL.
- A website will open where you need to enter the passcode obtained from the earlier cell.
- Click the blue "Submit" button to proceed.

### 7. Use the Streamlit App
- After submitting the passcode, the Streamlit app will load. You can now upload provided PDF files, ask questions, and retrieve answers using the RAG model.

---

Created by **Pranjal Kumar Sinha**.