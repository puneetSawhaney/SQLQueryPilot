<!DOCTYPE html>
<html lang="en">
<head>
</head>
<body>

  <h1>SQLQuery Pilot</h1>
  <p>A text-to-SQL analytics platform that lets you ask questions in plain English and get real database results instantly. Built for non-technical users who need to explore data without writing SQL.</p>

  <hr>

  <h2>What it does</h2>
  <p>You type a question like <em>"What were the top 5 products by revenue last month?"</em> and the system figures out the right SQL query, runs it against your database, and shows you the results — no SQL knowledge required.</p>

  <hr>

  <h2>Features</h2>
  <ul>
    <li>Chat-based query interface</li>
    <li>AI-powered SQL generation using GPT-4o</li>
    <li>Schema retrieval using vector search (ChromaDB + RAG)</li>
    <li>Semantic layer for business-aware querying</li>
    <li>Few-shot learning for more accurate SQL output</li>
    <li>Safety guard that blocks destructive queries (DELETE, DROP, etc.)</li>
    <li>Human-in-the-loop approval for risky operations</li>
    <li>Interactive results table with sorting</li>
    <li>Schema explorer with active table highlighting</li>
    <li>Query logging and observability</li>
  </ul>

  <hr>

  <h2>Architecture</h2>
  <pre>
Frontend (React)
    |
FastAPI Backend
    |
LangChain Pipeline (RAG + LLM)
    |
HITL Safety Guard
    |
SQL Execution (SQLAlchemy)
    |
Database (Star Schema)
    |
ChromaDB (Vector Store)
  </pre>

  <hr>

  <h2>How It Works</h2>
  <ol>
    <li>User enters a question in plain English</li>
    <li>System retrieves relevant schema context using vector search</li>
    <li>GPT-4o generates a SQL query using the schema and few-shot examples</li>
    <li>A safety guard validates the query before execution</li>
    <li>The query runs on the database</li>
    <li>Results are displayed in an interactive table</li>
  </ol>

  <hr>

  <h2>Tech Stack</h2>

  <h3>Frontend</h3>
  <p>React, TypeScript, Vite, Axios</p>

  <h3>Backend</h3>
  <p>FastAPI, SQLAlchemy, LangChain</p>

  <h3>AI / Data</h3>
  <p>OpenAI GPT-4o, ChromaDB, RAG Architecture</p>

  <h3>Infrastructure</h3>
  <p>nginx, systemd, AWS EC2</p>

  <hr>

  <h2>Project Structure</h2>
  <pre>
frontend/    React UI
api/         FastAPI routes
agent/       AI pipeline (RAG + SQL generation)
model/       Database schema and engine
data/        Dataset and seeding scripts
infra/       Deployment configuration
  </pre>

  <hr>

  <h2>Setup</h2>

  <h3>1. Clone the repository</h3>
  <pre>
git clone https://github.com/puneetSawhaney/SQLQueryPilot.git
cd querymind-ai
  </pre>

  <h3>2. Install backend dependencies</h3>
  <pre>
pip install -r requirements.txt
cp .env.example .env
  </pre>
  <p>Add your OpenAI API key to the <code>.env</code> file.</p>

  <h3>3. Seed the database</h3>
  <pre>python -m data.seed</pre>

  <h3>4. Build the vector index</h3>
  <pre>python -m agent.build_index</pre>

  <h3>5. Start the backend</h3>
  <pre>uvicorn api.main:app --reload</pre>

  <h3>6. Start the frontend</h3>
  <pre>
cd frontend
npm install
npm run dev
  </pre>

  <hr>

  <h2>Access</h2>
  <ul>
    <li>Frontend: <a href="http://localhost:5173">http://localhost:5173</a></li>
    <li>API Docs: <a href="http://localhost:8000/api/docs">http://localhost:8000/api/docs</a></li>
  </ul>

  <hr>

  <h2>Safety</h2>
  <ul>
    <li>Blocks all destructive SQL operations by default — DELETE, DROP, TRUNCATE, and similar commands are rejected before execution.</li>
    <li>Queries flagged as risky are held for manual approval before they run.</li>
    <li>Designed to be safe by default in production environments without extra configuration.</li>
  </ul>

  <hr>

  <h2>Planned Improvements</h2>
  <ul>
    <li>Role-based access control</li>
    <li>Query caching with Redis</li>
    <li>Data visualization (charts)</li>
    <li>Multi-database support</li>
    <li>Streaming responses</li>
  </ul>

  <hr>

  <p>Built by <strong>Puneet Sawhaney</strong></p>
  <p>If you find this useful, give it a star on GitHub.</p>

</body>
</html>
