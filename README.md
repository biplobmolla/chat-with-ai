# 🧠 Multi-AI Chat Web App

A real-time chat application that lets you communicate with multiple AI chatbots (like ChatGPT, Gemini, Claude, Grok, and more) from a single interface. Only you have a profile — all responses come from AI bots.

---

## ✨ Features

- 🗨️ **WhatsApp-style Chat UI**  
  A familiar and clean interface for smooth conversations.

- 📣 **Mention-Based Response System**  
  - Mention a specific bot (e.g., `@ChatGPT`) to get a reply only from that bot.
  - Skip mentions to broadcast your message to all bots.

- ⚡ **Real-Time Messaging**  
  - Uses **Socket.IO** for fast, live updates.
  - Bots respond based on their actual response time (first come, first shown).

- 🤖 **Multi-Bot Integration**  
  - Connects to different AI APIs (e.g., OpenAI for ChatGPT, Google Gemini, etc.).
  - Modular bot system for easily adding/removing integrations.

---

## 🛠️ Tech Stack

- **Frontend:** [Next.js](https://nextjs.org/) + TypeScript  
- **Backend:** [Express.js](https://expressjs.com/)  
- **Real-Time:** [Socket.IO](https://socket.io/)  
- **Styling:** Tailwind CSS (or your preferred CSS solution)  
- **Optional:** Database (PostgreSQL, MongoDB, etc.) for storing chat history

---

## 🚀 How It Works

1. You type a message.
2. If a specific bot is mentioned (`@Gemini`, `@Claude`, etc.), only that bot responds.
3. If no bot is mentioned, your message is sent to all bots.
4. Each bot processes the message asynchronously.
5. Responses are streamed back and displayed in the order they arrive.

---

## 🧩 Bot Integration (Pluggable System)

Each bot is integrated via a simple interface:

```ts
interface Bot {
  name: string;
  mentionTag: string;
  sendMessage: (message: string) => Promise<string>;
}
