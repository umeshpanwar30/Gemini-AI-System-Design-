# Gemini-AI-System-Design-


│                          CLIENT (ANDROID APP)                            │
│                                                                          │
│  ┌────────────────────────────────────────────────────────────────────┐  │
│  │                     JETPACK COMPOSE UI LAYER                       │  │
│  │  • Chat Screen (Typing Input)     • Titles List (LazyColumn)       │  │
│  └──────────────────────────────────┬─────────────────────────────────┘  │
│                                     │                                    │
│                        User Actions │ (User Types & Clicks Send)         │
│                        as "Intents" │ e.g., ChatIntent.SendMessage       │
│                                     ▼                                    │
│  ┌────────────────────────────────────────────────────────────────────┐  │
│  │                            VIEWMODEL                               │  │
│  │  • Processes Intents             • Dispatches Single UiState       │  │
│  │  • Handles UiEffect (Errors)     • StateFlow Pipeline              │  │
│  └──────────────────────────────────┬─────────────────────────────────┘  │
│                                     │                                    │
│               Asynchronous Network  │ (Retrofit Client / HTTP Requests)  │
│               Coroutines Call       │ Handles Network Interceptors       │
│                                     ▼                                    │
└─────────────────────────────────────┼────────────────────────────────────┘
                                      │
                                      │ (Secure API Call)
                                      ▼
┌──────────────────────────────────────────────────────────────────────────┐
│                        BACKEND SERVICE (FastAPI)                         │
│                                                                          │
│  ┌────────────────────────────────────────────────────────────────────┐  │
│  │                            API GATEWAY                             │  │
│  │  • Auth Routers / JWT Handling    • Chat Routers (Endpoints)       │  │
│  └──────────────────────────────────┬─────────────────────────────────┘  │
│                                     │                                    │
│                        Asynchronous │ (Python async/await Coroutines)    │
│                        Process      │ Secure API Key Isolation           │
│                                     ▼                                    │
└─────────────────────────────────────┼────────────────────────────────────┘
                                      │
                                      │ (Python SDK Integration)
                                      ▼
┌──────────────────────────────────────────────────────────────────────────┐
│                         THIRD-PARTY AI SERVICE                           │
│                                                                          │
│  ┌────────────────────────────────────────────────────────────────────┐  │
│  │                           GEMINI AI API                            │  │
│  │  • Processes Prompt Generation    • Returns Text Output            │  │
│  └────────────────────────────────────────────────────────────────────┘  │
└──────────────────────────────────────────────────────────────
