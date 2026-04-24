# coachella-resource 🎡 Coachella AI Assistant
📌 Overview

The Coachella AI Assistant is an interactive chatbot designed to help users plan their festival experience. It uses an AI agent built with LangChain and a web interface powered by Streamlit to provide personalized recommendations, schedule information, and budget estimates. This tool is intended for festival attendees who want a smarter, faster way to organize their trip.-bot

❗ The Problem

Planning a large music festival like Coachella can be overwhelming. Users must navigate artist schedules, discover new performers, and estimate costs across tickets, food, and transportation. Most information is scattered across different sources, requiring time-consuming searching and decision-making. This project addresses that frustration by centralizing key planning tools into a single conversational assistant, allowing users to quickly get relevant, personalized answers without switching between multiple apps or websites.
⚙️ How It Works
🧠 System Architecture
User → Streamlit UI → LangChain Agent
                         ↓
        ┌───────────────┼────────────────┐
        ↓               ↓                ↓
   Schedule Tool   Recommendation Tool   Budget Tool
        ↓               ↓                ↓
              Festival Data (data.py)
🔧 Tools Available
🎤 Schedule Tool
Retrieves performance times for specific artists.
🎧 Recommendation Tool
Suggests artists based on a user’s preferred genre.
💸 Budget Tool
Estimates total festival cost based on number of days and VIP status.
🤖 Decision Logic

The LangChain agent uses function-calling to decide which tool to invoke based on user input. For example:

If a user asks “When is Drake performing?” → Schedule Tool
If a user asks “Recommend electronic artists” → Recommendation Tool
If a user asks “Estimate budget for 3 days VIP” → Budget Tool

The agent can also maintain conversation memory, allowing it to respond more contextually across multiple turns.
🧠 Key Findings / What I Learned

One of the most surprising aspects of this project was how powerful tool-based agents are compared to basic chatbots. Instead of simply generating text, the model can make decisions and call specific functions, which makes the interaction feel much more useful and “real.” This shifted my understanding of AI from something that only answers questions to something that can actively assist with tasks.

A major challenge was structuring inputs for tools—especially the budget calculator—so that the agent could reliably parse user intent. Small formatting issues could cause tools to fail, which highlighted the importance of clear input design. If I were to improve this project, I would implement more robust parsing (or natural language handling) and connect to real-world festival data using a retrieval system (RAG) instead of hardcoded values.

💬 Sample Conversations
🎤 Schedule Tool Example

User: When is Drake performing?
Bot: Drake performs Friday at 8:30 PM

🎧 Recommendation Tool Example

User: Recommend rap artists
Bot: Try: Drake, Travis Scott

💸 Budget Tool Example

User: Estimate budget for 3 days, vip false
Bot: Estimated budget: $470

🔄 Multi-turn (Memory Example)

User: I like electronic music
Bot: You should check out Fred Again

User: When do they perform?
Bot: Fred Again performs Saturday at 10:00 PM

▶️ How to Run
📦 Dependencies

Install required packages:
pip install -r requirements.txt 

🔐 Setup

Create a .env file and add your API key:
OPENAI_API_KEY=your_key_here

🚀 Launch the App
streamlit run app.py
This will open the chatbot interface in your browser.

👥 Who Would Care

This tool would be useful for music festival attendees who want to efficiently plan their experience without juggling multiple sources of information. It could also benefit event organizers looking to improve user engagement through AI-driven assistants. More broadly, this project demonstrates how AI agents can support decision-making in real-world scenarios involving scheduling, budgeting, and personalized recommendations.
