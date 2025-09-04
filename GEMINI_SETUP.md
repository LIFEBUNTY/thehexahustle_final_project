# Google Gemini Setup Guide

## Get Free Gemini API Key

1. **Go to Google AI Studio**
   - Visit: https://makersuite.google.com/app/apikey
   - Sign in with your Google account

2. **Create API Key**
   - Click "Create API Key"
   - Select "Create API key in new project" 
   - Copy the generated API key

3. **Update Environment**
   - Add to `backend/.env`:
   ```env
   GEMINI_API_KEY=your_gemini_api_key_here
   AI_PROVIDER=gemini
   ```

## Features

✅ **Free Tier**: 60 requests per minute  
✅ **No Billing Required**: Completely free to start  
✅ **Image Analysis**: Gemini Pro Vision for crop disease detection  
✅ **Text Generation**: Gemini Pro for agricultural advice  
✅ **Multilingual**: Supports all Indian languages  

## Switch Between Providers

Change `AI_PROVIDER` in backend/.env:
- `AI_PROVIDER=gemini` (Free, no billing)
- `AI_PROVIDER=openai` (Requires billing)

## Test Gemini Connection

```bash
cd backend
npm install
npm run test:apis
```

Gemini is now your default AI provider! 🚀