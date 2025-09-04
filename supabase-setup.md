# Supabase Setup Guide

## Step 1: Create Supabase Project

1. Go to https://supabase.com
2. Click "Start your project"
3. Sign up/Login with GitHub
4. Click "New Project"
5. Choose organization
6. Fill project details:
   - Name: `digital-krishi-officer`
   - Database Password: (generate strong password)
   - Region: `Southeast Asia (Singapore)` (closest to India)
7. Click "Create new project"
8. Wait 2-3 minutes for setup

## Step 2: Get Project Credentials

1. Go to Settings > API
2. Copy these values:
   - Project URL
   - Project API keys (anon/public key)
   - Service role key (keep secret)

## Step 3: Run Database Schema

1. Go to SQL Editor in Supabase dashboard
2. Click "New query"
3. Copy and paste the schema from `backend/database/schema.sql`
4. Click "Run" to execute

## Step 4: Configure Authentication

1. Go to Authentication > Settings
2. Enable Email authentication
3. Set Site URL: `http://localhost:5173`
4. Add Redirect URLs:
   - `http://localhost:5173`
   - `http://localhost:5173/**`

## Step 5: Update Environment Files

### Frontend (.env)
```env
VITE_API_URL=http://localhost:5000/api
VITE_SUPABASE_URL=https://your-project-id.supabase.co
VITE_SUPABASE_ANON_KEY=your_anon_key_here
```

### Backend (backend/.env)
```env
PORT=5000
NODE_ENV=development

SUPABASE_URL=https://your-project-id.supabase.co
SUPABASE_ANON_KEY=your_anon_key_here
SUPABASE_SERVICE_KEY=your_service_role_key_here

OPENAI_API_KEY=your_openai_key_here
OPENWEATHER_API_KEY=your_weather_key_here
JWT_SECRET=your_super_secret_jwt_key_minimum_32_characters_long
```

## Step 6: Test Connection

Run this test to verify setup:
```bash
cd backend
node -e "
const { createClient } = require('@supabase/supabase-js');
const supabase = createClient('YOUR_URL', 'YOUR_ANON_KEY');
supabase.from('profiles').select('*').limit(1).then(console.log);
"
```

## Quick Setup Commands

```bash
# Install Supabase CLI (optional)
npm install -g supabase

# Test database connection
supabase db ping --project-ref your-project-id
```

Your Supabase project is ready! 🚀