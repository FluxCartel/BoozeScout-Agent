# BoozeScout Agent

An AI-powered assistant to find the best local prices for beer, wine, and spirits using price scouting, a chat assistant, and a voice-controlled live agent. This project is built with React, TypeScript, and the Google Gemini API.

## ✨ Features

-   **Price Scout:** A powerful search interface to find beverage prices from local stores.
    -   Search by product name.
    -   Filter by category, sub-category, and variety.
    -   Scan a product's barcode to search automatically.
    -   Use your device's geolocation to find stores nearby.
-   **Chat Assistant:** A conversational AI, powered by Gemini, to help you with:
    -   Beverage recommendations.
    -   Food pairing suggestions.
    -   General knowledge about wine, beer, and spirits.
    -   Text-to-speech functionality to read answers aloud.
-   **Live Agent:** A hands-free, voice-controlled interface.
    -   Start a conversation with the live agent.
    -   Tell it what product you're looking for and your location.
    -   The agent uses function calling to trigger a search in the Price Scout tab.
    -   Features real-time voice-in, voice-out, and on-screen transcription.

## 🛠️ Tech Stack

-   **Frontend:** React, TypeScript, Tailwind CSS
-   **AI:** Google Gemini API
    -   `gemini-2.5-pro` for Price Scout searches with Google Search & Maps grounding.
    -   `gemini-2.5-flash` for the Chat Assistant.
    -   `gemini-2.5-flash-preview-tts` for text-to-speech.
    -   `gemini-2.5-flash-native-audio-preview-09-2025` for the Live Agent.
-   **Dependencies:** Served via an `importmap` from a CDN, no `npm` or build step required.

## 🚀 Getting Started

This project is designed to be simple to run, with no complex build setup.

### Prerequisites

-   A modern web browser that supports `importmap`.
-   A **Google Gemini API Key**.

### Configuration

The application requires a Google Gemini API key to function.

1.  **Locate the `config.js` file** in the project's root directory.
2.  **Open the file** and replace the placeholder text `"YOUR_GEMINI_API_KEY_GOES_HERE"` with your actual API key.
3.  **Save the file.**

**⚠️ Important:** The `config.js` file contains your secret API key. **Do not commit this file to public version control like GitHub.** If you are using Git, you should add `config.js` to your `.gitignore` file.

### Running Locally

Since there is no build process, you just need a simple local web server to serve the project files.

1.  **Clone the repository (if you haven't already):**
    ```bash
    git clone https://github.com/your-username/boozescout-agent.git
    cd boozescout-agent
    ```

2.  **Set up your API Key** by following the "Configuration" steps above.

3.  **Start a local server:**
    If you have Python installed:
    ```bash
    python -m http.server
    ```
    Or if you have Node.js installed:
    ```bash
    npx serve
    ```

4.  Open your browser and navigate to the local address provided by the server (e.g., `http://localhost:8000` or `http://localhost:3000`).

## 📂 Project Structure

```
.
├── components/         # Reusable React components (Header, Spinner, etc.)
├── services/           # Logic for interacting with the Gemini API
├── utils/              # Helper functions (e.g., audio processing)
├── views/              # Main UI views for each tab (HomeScreen, PriceScoutView, etc.)
├── App.tsx             # Main application component, handles routing
├── constants.tsx       # Shared constants (tab names, category data)
├── index.html          # The main HTML entry point with importmap
├── index.tsx           # React root renderer
├── config.js           # <-- YOUR API KEY GOES HERE (DO NOT COMMIT)
└── types.ts            # TypeScript interfaces and type definitions
```
