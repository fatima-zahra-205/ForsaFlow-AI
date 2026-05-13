**ForsaFlow AI**

*Your Intelligent Career Companion & Job Search Assistant*

[Python](https://camo.githubusercontent.com/e9b1ec8ced0c12b3c79254c57eb36f6e8f89026b9f64bf5b01b971845997bb0b/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f507974686f6e2d332e392b2d626c75652e737667)

[Streamlit](https://camo.githubusercontent.com/8c7a10c45498ca97b927623fadcae6dd9d7db93d631de178d2f492407ba67977/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f53747265616d6c69742d4170702d4646344234422e737667)

[OpenAI](https://camo.githubusercontent.com/0d69e46bd8230c7b49efa7e9a0d3a177e69ee01828433316bb99768d3cb26d41/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4f70656e41492d4750542d2d342d3431323939312e737667)

[SQLite](https://camo.githubusercontent.com/f994e0f9fedc44e57481cb000f7b8cacd419d41b05b1d2911caf3220d613b0d9/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f53514c6974652d44617461626173652d3030334235372e737667)

> **ForsaFlow AI** is an advanced, AI-powered career accompaniment platform. Originally developed as an academic capstone project (PFE), it provides an end-to-end toolkit to optimise the job search experience with a localised focus on the Moroccan job market.
> 

**✨ Key Features**

- **🧠 Intelligent CV Analysis (`CVAnalyzer`)**
    - **Multi-Format Support:** Extracts text and data from standard PDFs, Image-based PDFs, DOCX, and standard image formats (via OCR).
    - **Hybrid AI ATS:** Uses both heuristic business rules and **GPT-4o-mini** to provide an industry-standard ATS score and deep semantic skill extraction.
    - **Market Localisation:** Calculates compatibility specifically tailored to the Moroccan job market (local keywords, French/Arabic/English language weighting).
- **🎯 Semantic Job Matching (`JobMatcher`)**
    - Goes beyond basic keyword matching! By utilising state-of-the-art NLP (`sentence-transformers`: `paraphrase-multilingual-MiniLM-L12-v2`), ForsaFlow calculates true cosine-similarity between the context of a candidate's profile and the nuances of a job description.
- **✍️ Contextual Document Generation (`DocGenerator`)**
    - Instantly generates highly tailored Cover Letters and professional LinkedIn outreach messages by merging a user's extracted CV metadata with the target job's requirements.
- **🎨 Professional CV Export (`CVExporter`)**
    - Transforms structured candidate data into a beautifully formatted, ready-to-download PDF CV aligned with modern design standards.
- **💬 AI Interview Coach (`InterviewCoach`)**
    - An integrated interactive chatbot designed to simulate real interview scenarios and provide constructive, real-time feedback.
- **📊 Integrated Applicant Tracking**
    - Built-in SQLite database allows users to track their applications, favourite job offers, and monitor their job hunt status over time.

---

**🏗️ Technical Architecture**

ForsaFlow AI relies on a clean, modular architecture separating the user interface from the underlying AI and data logic:

**Unable to render rich display**

Cannot read properties of undefined (reading 'render')

For more information, see https://docs.github.com/get-started/writing-on-github/working-with-advanced-formatting/creating-diagrams#creating-mermaid-diagrams

`graph TD
    User((User)) <--> UI[Streamlit UI]
    
    subgraph "Core AI & Logic Layer"
        UI <--> CV[CVAnalyzer - OpenAI/OCR]
        UI <--> JM[JobMatcher - Sentence-Transformers]
        UI <--> DG[DocGenerator - GPT-4]
        UI <--> CE[CVExporter - FPDF2]
        UI <--> IC[InterviewCoach - AI Chat]
    end
    
    subgraph "Data & Persistence"
        CV --> DB[(SQLite Database)]
        JM --> Scraper[Scraper - BS4]
        UI --> Emp[Employer Directory]
    end
    
    subgraph "External APIs"
        CV <--> OpenAI[OpenAI API]
        DG <--> OpenAI
    end`

**🚀 Installation & Setup**

To run ForsaFlow AI locally on your machine, follow these steps:

**1. Clone the repository**

```
git clone https://github.com/your-username/forsaflow-ai.git
cd forsaflow-ai
```

**2. Set up the Python Environment**

Ensure you have **Python 3.9 or higher** installed. It is recommended to use a virtual environment.

```
python -m venv .venv
# On Windows:
.venv\Scripts\activate
# On Linux/macOS:
source .venv/bin/activate
```

**3. Install Dependencies**

```
pip install -r requirements.txt
```

*(Note: For OCR features to work properly, you may need to install `tesseract-ocr` on your system natively).*

**4. Environment Variables**

Create a `.env` file in the root directory based on the provided `.env.example`:

```
OPENAI_API_KEY=your_openai_api_key_here
```

**5. Launch the Application**

Run the Streamlit server:

```
streamlit run app.py
```

Wait a few seconds, and the app will become available at `http://localhost:8501`.

**📸 Screenshots**

- **Dashboard View**: `![Dashboard](/path/to/image.png)`
- **CV Analyzer in Action**: `![CV Analyzer](/path/to/image.png)`
- **Mock Interview Chat**: `![Interview Chat](/path/to/image.png)`

**💻 Technologies Used**

- **Frontend:** [Streamlit](https://streamlit.io/)
- **Backend / AI:** Python, LangChain, `sentence-transformers`, OpenAI GPT-4
- **Data Parsing:** BeautifulSoup4 (BS4), PyPDF2, Tesseract OCR
- **Database:** SQLite (`forsaflow.db`)
- **Styling / Export:** FPDF2

**🎓 About This Project**

This project was developed as a Final Year Academic Project (PFE - Projet de Fin d'Études). The primary goal was to bridge the gap between talented candidates and the specifics of the Moroccan corporate landscape using cutting-edge Generative AI and NLP tools.

**📄 License**

This project is licensed under the MIT License - see the [LICENSE](https://github.com/fatima-zahra-AF207/ForsaFlow-AI/blob/main/LICENSE) file for details.
