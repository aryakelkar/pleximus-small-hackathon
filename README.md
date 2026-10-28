# 🧠 Pleximus AI - Cognitive Agent Workspace
**Day 1 · FAMT Ratnagiri · Department of AI & ML**

Pleximus AI is an innovative, interactive, and voice-enabled **AI Agent Workspace** designed to showcase advanced tool-calling and cognitive routing. The backend is built entirely with Python using only the **standard library** (for the web server and logical routing) and **`requests`** (for API calls), ensuring zero-configuration compatibility on lab machines. The frontend is a beautiful, glassmorphic single-page dashboard featuring real-time state tracking and voice interaction.


## 🚀 Key Features (Innovative & Unique)

1. **Voice Mode (Hands-Free Control)**:
   - **Speech-to-Text**: Click the microphone icon to speak a command (e.g. *"What is the weather in Ratnagiri?"*).
   - **Text-to-Speech**: Toggle the voice icon to have the agent speak its final parsed response out loud.
   - *Uses 100% native browser Web Speech APIs—no paid cloud voice translation or library setup needed!*

2. **"Agent Mind" Execution Visualizer**:
   - Displays a dynamic, glowing flowchart that lights up corresponding to the agent's current stage (`SYSTEM IDLE` ➔ `GEMINI ANALYSIS` ➔ `TOOL EXECUTION` ➔ `RESPONDING`).
   - A live-updating **Mind Inspector panel** displays raw JSON data for every API query, tool parameters, and tool responses, following the rule: *"Always print/log raw JSON."*

3. **Dynamic Context Cards**:
   - The side dashboard features cards that dynamically populate depending on the tool the agent calls!
   - Weather queries trigger a detailed weather dashboard card.
   - GitHub queries display stars, forks, and language statistics.
   - Wikipedia lookups render summary extracts with thumbnail pictures.
   - Currency conversions show a live currency calculator card.

4. **Synchronized In-Memory To-Do Checklist**:
   - Stateful To-Do list tool tracks tasks. The UI polls the state continuously, so when the agent executes tasks (e.g., *"Add code tests to my to-do list"*), the checklist updates in real-time.

5. **12 Powerful Registered Tools**:
   - **Core Tools**: Calculator (safe parsed evaluation), Weather Lookup (coordinates geocoding + Open-Meteo), and Word/Text Utility.
   - **Extension Tools**: GitHub Repository Lookup, Unit Converter (weight, length, temp), Currency Converter (Frankfurter API), Wikipedia Summarizer, World Clock & Timezone Tool (TimeAPI.io), Prime & Fibonacci Analyzer, Random Joke/Trivia Fetcher, and DuckDuckGo Stub Search.

---

## 🛠️ File Structure

- [`app.py`](file:///c:/Users/Lenovo/Downloads/pleximus%20hackathon/app.py): Entrypoint starting the python HTTP server (routing files & APIs).
- [`agent.py`](file:///c:/Users/Lenovo/Downloads/pleximus%20hackathon/agent.py): Manages conversational history and coordinates Gemini Function Calling loop.
- [`tools.py`](file:///c:/Users/Lenovo/Downloads/pleximus%20hackathon/tools.py): Implementation of all 12 tools and their JSON schemas.
- [`templates/index.html`](file:///c:/Users/Lenovo/Downloads/pleximus%20hackathon/templates/index.html): HTML5 Glassmorphism dashboard, JS voice recognition/speech, dynamic widgets, and visualizer.
- [`test_tools.py`](file:///c:/Users/Lenovo/Downloads/pleximus%20hackathon/test_tools.py): Unittest suite verifying calculation, string utility, units, todo state, and prime logic.

---

## 💻 Setup & How to Run

1. **Verify Dependencies**:
   Ensure python 3 is installed along with the requests library:
   ```bash
   pip install requests
   ```

2. **Run the Tests**:
   Before launching, you can run the test suite to verify tool accuracy:
   ```bash
   python -m unittest test_tools.py
   ```

3. **Launch the Workspace**:
   Start the local backend server:
   ```bash
   python app.py
   ```

4. **Access the Dashboard**:
   Open your browser and navigate to **`http://localhost:8000`**. The browser should launch automatically.

5. **Configure API Key**:
   - Click the **System Config** button on the top right.
   - Input your Google AI Studio Gemini API Key (get one free at [aistudio.google.com](https://aistudio.google.com)).
   - Save changes. The settings are saved in your local browser storage securely.
