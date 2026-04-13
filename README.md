<!DOCTYPE html>
<html lang="en">
<body>
<div class="wrap">

  <!-- Header -->
  <header>
    <h1>SQLQuery<span>Pilot</span></h1>
    <p class="tagline">Ask questions in plain English. Get SQL queries and real database results instantly — no SQL knowledge required.</p>
  </header>

  <!-- What it does -->
  <section>
    <h2>Overview</h2>
    <p>SQLQuery Pilot is a text-to-SQL analytics platform that converts natural language into SQL queries using large language models. You type a question like <em style="color:#cbd5e1">"What were the top 5 products by revenue last month?"</em> and the system generates the right SQL, runs it against your database, and displays the results — all without writing a single line of SQL.</p>
    <p>It is built for non-technical users who need to explore complex datasets without relying on engineers or analysts for every query.</p>
  </section>

  <!-- Features -->
  <section>
    <h2>Features</h2>
    <div class="feature-grid">
      <div class="feature-item"><div class="feature-dot"></div><span>Chat-based query interface</span></div>
      <div class="feature-item"><div class="feature-dot"></div><span>AI-powered SQL generation via GPT-4o</span></div>
      <div class="feature-item"><div class="feature-dot"></div><span>RAG-based schema retrieval with ChromaDB</span></div>
      <div class="feature-item"><div class="feature-dot"></div><span>Semantic layer for business-aware queries</span></div>
      <div class="feature-item"><div class="feature-dot"></div><span>Few-shot learning for accurate SQL output</span></div>
      <div class="feature-item"><div class="feature-dot"></div><span>Human-in-the-loop safety approval</span></div>
      <div class="feature-item"><div class="feature-dot"></div><span>Blocks destructive SQL by default</span></div>
      <div class="feature-item"><div class="feature-dot"></div><span>Interactive results table with sorting</span></div>
      <div class="feature-item"><div class="feature-dot"></div><span>Schema explorer with table highlighting</span></div>
      <div class="feature-item"><div class="feature-dot"></div><span>Query logging and observability</span></div>
    </div>
  </section>

  <!-- Architecture -->
  <section>
    <h2>Architecture</h2>
    <div class="arch-flow">
      <div class="arch-node highlight">Frontend (React)</div>
      <div class="arch-arrow"></div>
      <div class="arch-node">FastAPI Backend</div>
      <div class="arch-arrow"></div>
      <div class="arch-node">LangChain Pipeline — RAG + LLM</div>
      <div class="arch-arrow"></div>
      <div class="arch-node">HITL Safety Guard</div>
      <div class="arch-arrow"></div>
      <div class="arch-node">SQL Execution — SQLAlchemy</div>
      <div class="arch-arrow"></div>
      <div class="arch-node">Database — Star Schema</div>
      <div class="arch-arrow"></div>
      <div class="arch-node highlight">ChromaDB — Vector Store</div>
    </div>
  </section>

  <!-- How it works -->
  <section>
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
  </section>

  <!-- Tech Stack -->
  <section>
    <h2>Tech Stack</h2>
    <div class="stack-group">
      <div class="stack-label">Frontend</div>
      <div class="pills">
        <span class="pill blue">React</span>
        <span class="pill blue">TypeScript</span>
        <span class="pill blue">Vite</span>
        <span class="pill blue">Axios</span>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-label">Backend</div>
      <div class="pills">
        <span class="pill">FastAPI</span>
        <span class="pill">SQLAlchemy</span>
        <span class="pill">LangChain</span>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-label">AI / Data</div>
      <div class="pills">
        <span class="pill purple">OpenAI GPT-4o</span>
        <span class="pill purple">ChromaDB</span>
        <span class="pill purple">RAG Architecture</span>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-label">Infrastructure</div>
      <div class="pills">
        <span class="pill green">nginx</span>
        <span class="pill green">systemd</span>
        <span class="pill green">AWS EC2</span>
      </div>
    </div>
  </section>

  <!-- Project Structure -->
  <section>
    <h2>Project Structure</h2>
    <div class="file-tree">
      <div class="file-row"><span class="dir">frontend/</span><span class="desc">React UI</span></div>
      <div class="file-row"><span class="dir">api/</span><span class="desc">FastAPI routes</span></div>
      <div class="file-row"><span class="dir">agent/</span><span class="desc">AI pipeline — RAG + SQL generation</span></div>
      <div class="file-row"><span class="dir">model/</span><span class="desc">Database schema and engine</span></div>
      <div class="file-row"><span class="dir">data/</span><span class="desc">Dataset and seeding scripts</span></div>
      <div class="file-row"><span class="dir">infra/</span><span class="desc">Deployment configuration</span></div>
    </div>
  </section>

  <!-- Setup -->
  <section>
    <h2>Setup</h2>

    <div class="setup-step">
      <h3><span class="n">01</span> Clone the repository</h3>
      <pre><span class="cmd">git clone</span>https://github.com/puneetSawhaney/SQLQueryPilot.git
<span class="cmd">cd</span> querymind-ai</pre>
    </div>

    <div class="setup-step">
      <h3><span class="n">02</span> Install backend dependencies</h3>
      <pre><span class="cmd">pip install</span> -r requirements.txt
<span class="cmd">cp</span> .env.example .env
<span class="comment"># Add your OpenAI API key to .env</span></pre>
    </div>

    <div class="setup-step">
      <h3><span class="n">03</span> Seed the database</h3>
      <pre><span class="cmd">python</span> -m data.seed</pre>
    </div>

    <div class="setup-step">
      <h3><span class="n">04</span> Build the vector index</h3>
      <pre><span class="cmd">python</span> -m agent.build_index</pre>
    </div>

    <div class="setup-step">
      <h3><span class="n">05</span> Start the backend</h3>
      <pre><span class="cmd">uvicorn</span> api.main:app --reload</pre>
    </div>

    <div class="setup-step">
      <h3><span class="n">06</span> Start the frontend</h3>
      <pre><span class="cmd">cd</span> frontend
<span class="cmd">npm install</span>
<span class="cmd">npm run dev</span></pre>
    </div>
  </section>

  <!-- Access -->
  <section>
    <h2>Access</h2>
    <div class="access-cards">
      <div class="access-card">
        <div class="label">Frontend</div>
        <div class="url">http://localhost:5173</div>
      </div>
      <div class="access-card">
        <div class="label">API Docs</div>
        <div class="url">http://localhost:8000/api/docs</div>
      </div>
    </div>
  </section>

  <!-- Safety -->
  <section>
    <h2>Safety</h2>
    <div class="safety-list">
      <div class="safety-item">Blocks all destructive SQL operations by default — DELETE, DROP, TRUNCATE, and similar commands are rejected before execution.</div>
      <div class="safety-item">Queries flagged as potentially risky are held for manual human approval before they run.</div>
      <div class="safety-item">Designed to be safe by default in production environments without additional configuration.</div>
    </div>
  </section>

  <!-- Planned improvements -->
  <section>
    <h2>Planned Improvements</h2>
    <div class="future-list">
      <div class="future-item">Role-based access control</div>
      <div class="future-item">Query caching with Redis</div>
      <div class="future-item">Data visualization — charts</div>
      <div class="future-item">Multi-database support</div>
      <div class="future-item">Streaming responses</div>
    </div>
  </section>

  <!-- Footer -->
  <footer>
    <div class="author">Built by <strong>Puneet Sawhaney</strong></div>
    <div class="star-note">If you find this useful, give it a star on GitHub.</div>
  </footer>

</div>
</body>
</html>
