# Lexsy - AI Legal Document Filler

Lexsy is an intelligent web application that streamlines the process of filling out legal document drafts. By leveraging Google's Gemini AI, it automatically identifies variable fields in your documents and guides you through a conversational interface to fill them in.

## 🚀 Try it Out
**Live Demo:** [https://lexsy-lbuk.onrender.com/](https://lexsy-lbuk.onrender.com/)

## 📂 Project Structure

```
lexsy/
├── app.py              # Main Flask application and backend logic
├── templates/
│   └── index.html      # Frontend UI (HTML/TailwindCSS/JS)
├── requirements.txt    # Python dependencies
├── Procfile            # Deployment configuration for Render/Heroku
├── .env.example        # Example environment variables
└── UPLOAD_FOLDER/      # Temporary storage for uploaded and generated files
```

## 🛠 How it Works

1.  **Upload**: Users drag and drop a legal draft (`.docx` or `.pdf`).
2.  **Analyze**: The backend extracts text from the document and sends it to Google's Gemini 2.0 Flash model.
3.  **Identify**: Gemini identifies dynamic placeholders (e.g., `[Client Name]`, `{{Date}}`) and generates a structured list of variables.
4.  **Chat**: The user interacts with a chat interface to provide values for each identified variable.
5.  **Generate**: The application replaces the placeholders in the original document with the user's answers and provides a download link.

> **Note:** Signature fields and complex formatting that requires manual review are intentionally left for the user to fill out manually in the final document.

## 📦 Dependencies

-   **Flask**: Web framework for the backend.
-   **google-genai**: Official SDK for accessing Google's Gemini models.
-   **python-docx**: For reading and writing `.docx` files.
-   **pypdf**: For extracting text from `.pdf` files.
-   **pydantic**: For defining structured data models for AI responses.
-   **gunicorn**: WSGI HTTP Server for production deployment.

## 🔧 Local Setup

1.  **Clone the repository:**
    ```bash
    git clone <your-repo-url>
    cd lexsy
    ```

2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Set up Environment Variables:**
    Create a `.env` file (or export directly) with your Google GenAI API key:
    ```bash
    export GENAI_API_KEY="your_api_key_here"
    ```

4.  **Run the application:**
    ```bash
    python3 app.py
    ```

5.  **Access the app:**
    Open `http://127.0.0.1:5001` in your browser.
