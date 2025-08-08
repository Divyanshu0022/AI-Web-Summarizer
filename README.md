# AI-Web-Summarizer
<img width="2048" height="2048" alt="Gemini_Generated_Image_y05w6sy05w6sy05w" src="https://github.com/user-attachments/assets/d6a38b63-4914-49f8-86ae-1d5eabfab15f" />

This project is a Python-based tool that automatically generates a professional marketing brochure for a company based on the content of its website. It combines web scraping with the power of multiple frontier AI models (from OpenAI, Anthropic, and Google), allowing users to create marketing materials instantly through a simple web interface.
<img width="1920" height="1080" alt="Screenshot (417)" src="https://github.com/user-attachments/assets/7e295e9d-1f11-4de6-8534-f5c3655de776" />

### **Features 🚀**
* **Multi-Model Support:** Choose between top-tier AI models (GPT-4o mini, Claude 3 Haiku, and Gemini 1.5 Flash) to generate content.
* **Simple Web Interface:** Built with Gradio, the UI allows anyone to easily input a company name and URL to get started.
* **Automated Content Extraction:** Intelligently scrapes and cleans text from any landing page, focusing only on relevant content.
* **Real-Time Generation:** The brochure text is streamed back to the user in real-time as the AI generates it.

### **Technology Used** ⚙️

- **AI Models & Libraries**
     - **GPT-4o mini (OpenAI):** A powerful and efficient model from OpenAI, accessed via the openai library.
     - **Claude 3 Haiku (Anthropic):** A fast and capable model from Anthropic, accessed via the anthropic library.
     - **Gemini 1.5 Flash (Google):** A lightweight, multimodal model from Google, accessed via the litellm library for unified API calls.

- **Web Interface**
      **Gradio:** Used to create and host the interactive and user-friendly web application.

- **Web Scraping**
      **Requests:** To fetch the raw HTML content from a URL.
      **BeautifulSoup4:** To parse the HTML, clean it by removing irrelevant tags (like scripts and styles), and extract the core text.

- **Environment**
      **Python 3:** The core programming language.

- **Jupyter Notebook:** An interactive environment for developing and demonstrating the code.

- **python-dotenv:** To securely manage API keys by loading them from a local .env file.
-----

### **Workflow** 🌊

1.  **Initialization:** The script begins by loading the necessary API key from a `.env` file to securely connect to the OpenAI service.
2.  **Fetch Content:** When a user provides a URL, the `requests` library sends a GET request to that URL to retrieve its HTML source code.
3.  **Clean and Extract:** The raw HTML is passed to `BeautifulSoup`, which parses the document. The code systematically removes non-content tags (`<script>`, `<style>`, etc.) to isolate the main article or body text.
4.  **Prompt Engineering:** The extracted text is then formatted into a structured prompt for the AI. This includes:
      * A **system prompt** that instructs the AI to act as a summarizing assistant.
      * A **user prompt** that provides the cleaned website text and asks for a summary.
5.  **AI Summarization:** This complete prompt is sent to the OpenAI API. The GPT-4o-mini model processes the text and generates a coherent, markdown-formatted summary.
6.  **Display Output:** The final brochure is streamed back and displayed in real-time within the Gradio interface for the user to see.

<img width="1852" height="611" alt="image" src="https://github.com/user-attachments/assets/3c73afc0-9c07-4fb3-a8c8-2303aa6647b4" />
<img width="1846" height="539" alt="image" src="https://github.com/user-attachments/assets/6d44c3da-0636-4cc1-8067-54c5cb8cde1b" />

-----

### **How to Run This Project** ▶️

To run this project on your own machine, you will need to set up your environment and provide your own API key.

1.  **Install Libraries:** Make sure you have the required Python libraries installed:
    ```bash
    pip install openai python-dotenv requests beautifulsoup4 jupyter
    ```
2.  **Get an API Key:** This project requires an **OpenAI API key**. You can get one by creating an account on the [OpenAI Platform](https://platform.openai.com/).
3.  **Set Up Your Environment File:**
      * In the root directory of the project, create a new file and name it exactly `.env`.
      * Open the `.env` file and add your API key in the following format:
        ```
        OPENAI_API_KEY=sk-proj...<your_api_key_here>
        ```
      * Save the file. The `python-dotenv` library will automatically load this key so you don't have to hardcode it in your script.

Once these steps are complete, you can run the Jupyter Notebook, and it will be able to connect to the OpenAI service to generate summaries.


Special thanks to Ed Donner for inspiring this project—his original code and insights were instrumental in shaping the AI summarization workflow
