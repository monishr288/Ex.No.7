# Exno.7-Develop a prompt-based application tailored to their personal needs, fostering creativity and practical problem-solving skills while leveraging the capabilities of large language models.

# Date: 14.5.25
# Register no: 212223220061
# Aim: To develop a prompt-based application using ChatGPT - To demonstrate how to create a prompt-based application to organize daily tasks, showing the progression from simple to more advanced prompt designs and their corresponding outputs.

#AI Tools Required: 


# Explanation: 
Prompt:
"Design a personal productivity assistant that can help manage daily tasks, schedule reminders, suggest wellness tips, and answer general queries. The assistant should interact using natural language and be adaptable to the user’s changing preferences over time."
Procedure:
1. Define the core requirements of a personal productivity assistant.
2. Identify and construct appropriate prompts for each task using an LLM (e.g., ChatGPT).
3. Simulate natural user interaction through a simple interface or command-line system.
4. Collect feedback or inputs from users and adapt responses accordingly.
5. (Optional) Integrate basic memory to simulate preference adaptation.
EXPECTED OUTPUT: - (attached the drive link)
Output (Example Response by LLM):
Personal Productivity Assistant Features:
1. Daily Task Manager:
o Accept tasks via natural language (e.g., "Remind me to call mom at 6 PM").
o Organize tasks by priority and deadline.
o Provide daily summaries and pending items.
2. Smart Scheduler:
o Schedule events and set reminders using contextual understanding.
o Notify user of overlapping appointments or free time slots.
3. Wellness Tips Generator:
o Suggest daily wellness advice (hydration, exercise, screen-time breaks).
o Adapt suggestions based on past user preferences and responses.
## OUTPUT :
## 🧠 Core Features
## ✅ 1. Daily Task Management
Add, remove, update, and prioritize tasks via natural language.

Example: “Remind me to call mom tomorrow at 6 PM.”

Persistent storage (SQLite or JSON for local, Firebase for cloud).

## ✅ 2. Smart Reminders
Use background scheduler (e.g., APScheduler) to notify user.

Adapt reminder times based on habits (e.g., prefers evening planning).

## ✅ 3. Wellness Tip Generator
Daily self-care/wellness tips based on user behavior or preferences.

Categories: mental health, hydration, screen breaks, mindfulness
## ✅ 4. Conversational Assistant
General knowledge Q&A.

Use LLM to summarize emails, generate summaries, or respond to queries like:

“What’s the best time to work out?”

“Summarize this article.”

## ✅ 5. User Personalization & Learning
Save preferences (e.g., reminder tone, task types, wake-up time).

Optional feedback loop: “Did this tip help?” → refine future suggestions.

## 🏗️ System Architecture Overview
```
[User Input (NL)] 
        ↓
[LLM/NLP Engine (OpenAI/GPT-4)]
        ↓
[Intent Parser & Task Router]
        ↓
[Feature Modules: Tasks | Reminders | Wellness | Q&A]
        ↓
[Persistent Storage (SQLite/JSON)]
        ↓
[Feedback + Preference Adapter]

```
## 💻 Python App Skeleton
```
from features.task_manager import TaskManager
from features.reminders import ReminderScheduler
from features.wellness import WellnessTips
from features.chatbot import GeneralAssistant

class ProductivityAssistant:
    def __init__(self):
        self.task_manager = TaskManager()
        self.reminder_scheduler = ReminderScheduler()
        self.wellness_tips = WellnessTips()
        self.chatbot = GeneralAssistant()

    def handle_input(self, user_input: str):
        if "remind me" in user_input.lower():
            return self.reminder_scheduler.schedule(user_input)
        elif "add task" in user_input.lower():
            return self.task_manager.add_task(user_input)
        elif "wellness" in user_input.lower():
            return self.wellness_tips.suggest_tip()
        else:
            return self.chatbot.answer(user_input)

```
## 🧠 Natural Language Integration (OpenAI)
```
import openai, os
openai.api_key = os.getenv("OPENAI_API_KEY")

class GeneralAssistant:
    def answer(self, query):
        response = openai.ChatCompletion.create(
            model="gpt-4",
            messages=[{"role": "user", "content": query}]
        )
        return response['choices'][0]['message']['content']

```
## 🧬 Adaptive Personalization
Store user preferences in a profile (e.g., JSON or small DB).

Example preferences:

Preferred time blocks for tasks

Tone of wellness tips (funny, professional)

Recurring tasks

## 🎨 Optional UI Layer
CLI: Start with command line interface.

Streamlit: Quick dashboard for web UI.

TUI/Chatbot: Use Gradio or LangChain for real-time interaction.

## 🧪 Sample Interaction
User: “Remind me to drink water every 2 hours.”
Assistant: “Hydration reminder scheduled every 2 hours. Stay refreshed!”

User: “Give me a wellness tip.”
Assistant: “Today’s tip: Take a 5-minute break every hour to stretch and rest your eyes.”

User: “Add task to finish the report by 3 PM.”
Assistant: “Task ‘finish the report’ scheduled before 3 PM today.”



# Result: 
The lab exercise resulted in the creation of a prototype concept for a personal assistant powered by large language models. Students were able to:
 Understand how to tailor LLM prompts to real-life applications.
 Foster creativity by designing features suited to their personal or academic lives.
 Learn prompt engineering techniques for optimal interaction with AI tools.
 Experience the versatility and utility of generative AI in solving everyday problems.
