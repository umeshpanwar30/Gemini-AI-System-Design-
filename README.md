# Gemini-AI-System-Design-

### System Architecture Flow


[Jetpack Compose UI Layer]
         │
         ▼ (User Intent: ChatIntent.SendMessage)
         │
    [ViewModel]
         │
         ▼ (Asynchronous HTTP Call via Retrofit)
         │
 [FastAPI Backend Gateway]
         │
         ▼ 
         │
    [Gemini AI API]
