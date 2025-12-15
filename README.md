<h1>Foundation Agent (Stage 0)</h1>

    <p>A minimal LLM-powered chatbot using Groq’s ChatCompletions API and Streamlit.
    This agent is intentionally simple: no memory, no grounding, no frameworks.
    It demonstrates how a raw LLM behaves before adding enterprise capabilities in later stages.</p>

    <hr>

    <h2>Repository Structure</h2>
    <p>
    <code>foundation_agent.py</code><br>
    <code>requirements.txt</code><br>
    <code>Procfile</code><br>
    <code>.python-version</code><br>
    <code>README.md</code>
    </p>

    <hr>

    <h2>Run Locally</h2>

    <ol>
        <li>Install dependencies:
<pre><code>pip install -r requirements.txt
</code></pre>
        </li>
        <li>Set your API key:
<pre><code>export GROQ_API_KEY="your_key_here"
</code></pre>
        </li>
        <li>Run the app:
<pre><code>streamlit run foundation_agent.py
</code></pre>
        </li>
    </ol>

    <hr>

    <h2>Deploying the App</h2>

    <p>You can deploy this same repository to either **Streamlit Cloud** or **Heroku**.</p>

    <hr>

    <h2>Deploy to Streamlit Cloud (recommended for simplicity)</h2>

    <p>Streamlit Cloud automatically detects Streamlit apps and requires no Procfile.</p>

    <h3>Prerequisites:</h3>
    <ul>
        <li>Sign up to obtain a free API key for Groq LLM: <a href="https://console.groq.com/keys">https://console.groq.com/keys</a></li>
        <li>Push this repo to your GitHub account.</li>
    </ul>

    <h3>Steps:</h3>
    <ol>
        <li>Go to <a href="https://share.streamlit.io">https://share.streamlit.io</a></li>
        <li>Connect your GitHub repository.</li>
        <li>Select <code>foundation_agent.py</code> as the entry point.</li>
        <li>Add an environment variable:
            <table>
                <thead>
                    <tr>
                        <th>Name</th>
                        <th>Value</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>GROQ_API_KEY</td>
                        <td>your_key</td>
                    </tr>
                </tbody>
            </table>
        </li>
        <li>Deploy.</li>
    </ol>

    <p>No <code>setup.sh</code> or runtime configuration is required.</p>

    <hr>

    <h2>Deploy to Heroku</h2>

    <p>Heroku uses the included <code>Procfile</code> and <code>.python-version</code>.</p>

    <h3>Prerequisites for all Heroku Options:</h3>
    <ul>
        <li>Sign up to obtain a free API key for Groq LLM: <a href="https://console.groq.com/keys">https://console.groq.com/keys</a></li>
        <li>Fork the repo: <a href="https://github.com/lightningexperience/mas_workshop_foundation_agent">https://github.com/lightningexperience/mas_workshop_foundation_agent</a></li>
    </ul>

    <h3>Option 1: Heroku CLI Deployment (Advanced)</h3>
    <p>This option requires you to download and install the **Heroku CLI**.</p>
    <ol>
        <li>**Login:**
<pre><code>heroku login
</code></pre>
        </li>
        <li>**Create an app:**
<pre><code>heroku create my-foundation-agent 
</code></pre>
        </li>
        <li>**Set environment variable:**
<pre><code>heroku config:set GROQ_API_KEY="your_key_here"
</code></pre>
        </li>
        <li>**Deploy:**
<pre><code>git push heroku main
</code></pre>
        </li>
        <li>**Open the app:**
<pre><code>heroku open
</code></pre>
        </li>
    </ol>

    <h3>Option 2: GitHub-Based Deployment (No CLI Required)</h3>
    <p>This option uses the Heroku web interface and GitHub integration.</p>
    <ol>
        <li>**Create App:** Log into Heroku and create a new app via the dashboard.</li>
        <li>**Add Monitoring (Optional):** Go to the app's **Resources** tab and search for and add the **Papertrail** add-on (free edition).</li>
        <li>**Connect GitHub:** Navigate to the **Deploy** tab:
            <ul>
                <li>Select **GitHub** as the deployment method.</li>
                <li>Connect your GitHub account and search for and select your **forked repository**.</li>
                <li>Under **Automatic deploys**, click **Enable Automatic Deploys**.</li>
            </ul>
        </li>
        <li>**Set API Key:** Go to the **Settings** tab and click **Reveal Config Vars**.
            <ul>
                <li>Set the config variable: <code>GROQ_API_KEY</code> to the value of your Groq API key.</li>
            </ul>
        </li>
        <li>**Initial Deploy:** Return to the **Deploy** tab and click **Deploy Branch** to build and launch your application.</li>
    </ol>

    <h3>One-click deployment:</h3>
    <p><a href="https://heroku.com/deploy"><img class="deploy-button" src="https://www.herokucdn.com/deploy/button.svg" alt="Deploy"></a></p>

    <hr>

    <h2>Procfile (already included)</h2>
    <pre><code>web: streamlit run foundation_agent.py --server.port=$PORT --server.address=0.0.0.0
</code></pre>

    <hr>

    <h2>.python-version (already included)</h2>
    <pre><code>3.11
</code></pre>
    <p>Heroku will automatically select the latest patch version (e.g., 3.11.14).</p>

    <hr>

    <h2>requirements.txt (already included)</h2>
    <pre><code>streamlit
groq
python-dotenv
</code></pre>

    <hr>

    <h2>Purpose of Stage 0</h2>

    <p>This agent represents the “raw LLM” stage:</p>
    <ul>
        <li>No conversational memory</li>
        <li>No grounding or retrieval</li>
        <li>No actions</li>
        <li>No enterprise frameworks</li>
        <li>No LangChain</li>
    </ul>

    <p>This stage helps users understand the limitations of a simple LLM before introducing more advanced features in later stages:
    Stage 1 (Enterprise Framework), Stage 2 (Grounding), Stage 3 (Action Agents), and Stage 4 (Orchestration).</p>
