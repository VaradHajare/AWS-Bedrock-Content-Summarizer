# 📄 AWS Bedrock Content Summarizer (AI For Bharat Week 1 Lab)
<img width="821" height="908" alt="Content_Summarizer" src="https://github.com/user-attachments/assets/c23418ac-ecfd-4047-a8d0-45e4929bb81b" />
 
A Generative AI application that leverages **AWS Bedrock** and **Anthropic Claude 3.7 Sonnet** to analyze and summarize PDF documents. This project demonstrates how to use the [AWS SDK for Python (Boto3)](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html) to interact with Foundation Models (FMs) and visualize the results using [Streamlit](https://streamlit.io/).

## 🚀 Features

* **PDF Document Processing:** Directly processes PDF files (specifically the Amazon Leadership Principles) without needing external OCR tools.
* **Custom Prompts:** Users can input natural language instructions to define how they want the summary generated (e.g., "Summarize in 3 bullet points" or "Explain like I'm 5").
* **Advanced AI Model:** Utilizes `us.anthropic.claude-3-7-sonnet-20250219-v1:0` via the AWS Bedrock Converse API.
* **Interactive UI:** A clean, browser-based interface built with Streamlit.

## 📂 Project Structure

Ensure your directory looks like this for the code to function:

```
AWS-Bedrock-Content-Summarizer/
│
├── app.py                                # The main Streamlit application
├── summarization_lib.py                  # The backend logic using Boto3
├── amazon-leadership-principles-*.pdf    # The PDF document to be analyzed
├── requirements.txt                      # List of dependencies
└── README.md                             # Project documentation
```

## 🛠️ Prerequisites

Before running this project, ensure you have:

1.  **Python 3.9+** installed.
2.  An **AWS Account** with active credentials.
3.  **Model Access:** You must enable **Claude 3.7 Sonnet** in the AWS Bedrock console (specifically in the `us-east-1` region based on the model ID).
4.  **AWS CLI** installed and configured with your credentials.

## 📥 Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/AWS-Bedrock-Content-Summarizer.git](https://github.com/your-username/AWS-Bedrock-Content-Summarizer.git)
    cd AWS-Bedrock-Content-Summarizer
    ```

2.  **Create a [Virtual Environment](https://docs.python.org/3/library/venv.html):**
    ```bash
    # Windows
    python -m venv .venv
    .venv\Scripts\activate

    # Mac/Linux
    python3 -m venv .venv
    source .venv/bin/activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install boto3 streamlit
    ```

4.  **Add the PDF:**
    Place the file named `amazon-leadership-principles-070621-us.pdf` in the root folder.

## 🏃‍♂️ Usage

Run the application using the Streamlit CLI:

```bash
streamlit run app.py
```

The application will launch in your default web browser at `http://localhost:8501`.

1.  Enter your instruction in the text area (e.g., *"What are the top 3 principles?"*).
2.  Click the **Summarize** button.
3.  View the AI-generated response.

## 🧠 Technical Highlights

* **Boto3 Converse API:** This project uses the `bedrock.converse()` method, which simplifies sending documents and messages to the model.
* **Binary Handling:** The PDF is read as raw bytes (`doc_file.read()`) and sent directly to the model, bypassing the need for complex Base64 encoding.
* **Deterministic Output:** The inference configuration is set to `temperature: 0`, ensuring consistent and factual responses from the model.

---
*This project is for educational purposes demonstrating Cloud and GenAI integration.*
