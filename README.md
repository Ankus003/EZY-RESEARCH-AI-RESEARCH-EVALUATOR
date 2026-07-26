<h1>🔬 EZYResearch</h1>


A multi-agent AI research pipeline that searches, reads, writes, and critiques — all on its own.

Gyst:
Give it a topic. Four specialized agents take it from there: one searches the web, one scrapes the best source for deeper context, one writes a structured report, and one critiques it like an editor. You get a polished, sourced research report in a few clicks.

Built with LangChain, LangGraph, and Streamlit, powered by open models via OpenRouter and live web data via Tavily.


<h3>🛠️Working Demo</h3>
https://youtu.be/ZiVFFO7H-NE

  
<h3>✨ Features</h3>
🔍 Search Agent — Pulls recent, reliable information from the web on any topic
📄 Reader Agent — Picks the most relevant result and scrapes it for deeper content
✍️ Writer Chain — Synthesizes everything into a structured, professional report (Introduction → Key Findings → Conclusion → Sources)
🧐 Critic Chain — Reviews the report and scores it out of 10, with strengths, weaknesses, and a one-line verdict
🎨 Custom-styled Streamlit UI — A dark, minimal, orange-accented interface with a live pipeline tracker showing each agent's status in real time
⬇️ One-click export — Download the final report as a .md file


<h3>🧠 How It Works</h3>
                     ┌──────────────────┐
   Topic  ────────▶  │   Search Agent    │  ── Tavily web search
                     └────────┬─────────┘
                              │  search results
                              ▼
                     ┌──────────────────┐
                     │   Reader Agent    │  ── scrapes top URL
                     └────────┬─────────┘
                              │  scraped content
                              ▼
                     ┌──────────────────┐
                     │   Writer Chain    │  ── drafts the report
                     └────────┬─────────┘
                              │  report
                              ▼
                     ┌──────────────────┐
                     │   Critic Chain    │  ── scores & reviews
                     └────────┬─────────┘
                              │
                              ▼
                    📝 Final Report + 🧐 Feedback

Each stage's output feeds directly into the next, so the final report is grounded in real, freshly-searched web content rather than the model's own memory.


<h3>📁 Project Structure</h3>

Ezy Research/
├── app.py              # Streamlit UI — the main entry point
├── pipeline.py          # CLI version of the pipeline (no UI)
├── agents.py            # Agent & chain definitions (search, reader, writer, critic)
├── tools.py              # Tool implementations (web_search, scrape_url)
└── requirements.txt      # Python dependencies


<h3>🛠️ Tech Stack</h3>
Layer	Tool
UI	Streamlit
Agent framework	LangChain + LangGraph
LLM	mistralai/mistral-small-3.2-24b-instruct via OpenRouter
Web search	Tavily API
Web scraping	requests + BeautifulSoup4


<h3>🚀 Getting Started</h3>
1. Clone & enter the project
bash
cd "Ezy Research"
2. Create a virtual environment (recommended)
bash
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
3. Install dependencies
bash
pip install -r requirements.txt
4. Set up your API keys

Create a .env file in the project root:

env
OPENROUTER_API_KEY=your_openrouter_api_key_here
TAVILY_API_KEY=your_tavily_api_key_here
Get an OpenRouter key at openrouter.ai
Get a Tavily key at tavily.com
5. Run the app

Streamlit UI (recommended):

bash
streamlit run app.py

Or the CLI pipeline:

bash
python pipeline.py


<h3>💡 Usage</h3>
Launch the app and enter a research topic (e.g. "Quantum computing breakthroughs in 2025")
Click ⚡ Run Research Pipeline
Watch the pipeline panel update live as each agent completes its step
Read the final report and critic feedback, or download the report as Markdown


<h3>🗺️ Roadmap Ideas</h3>
 Support multiple sources in the Reader Agent (not just one URL)
 Let users choose the LLM/model from the UI
 Add citation-linking directly inside the report text
 Export reports as PDF/DOCX in addition to Markdown
 Add report history / session persistence


<h3>📄 License</h3>

Add your preferred license here (e.g. MIT).
