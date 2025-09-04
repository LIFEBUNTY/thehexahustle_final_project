# Digital Krishi Officer - Complete Setup Guide

This guide will help you set up the complete Digital Krishi Officer platform with all backend services.

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ installed
- Git installed
- Supabase account
- OpenAI API account
- OpenWeatherMap API account

## 📋 Step-by-Step Setup

### 1. Clone and Install Dependencies

```bash
# Navigate to project directory
cd hhp_final_1

# Install frontend dependencies
npm install

# Install backend dependencies
cd backend
npm install
cd ..
```

### 2. Create Supabase Project

1. Go to [Supabase](https://supabase.com)
2. Create new project
3. Go to Settings > API
4. Copy your project URL and anon key
5. Go to SQL Editor
6. Run the schema from `backend/database/schema.sql`

### 3. Get API Keys

#### OpenAI API Key
1. Go to [OpenAI Platform](https://platform.openai.com)
2. Create account and add billing
3. Go to API Keys section
4. Create new API key

#### OpenWeatherMap API Key
1. Go to [OpenWeatherMap](https://openweathermap.org/api)
2. Sign up for free account
3. Go to API Keys section
4. Copy your API key

### 4. Configure Environment Variables

#### Backend Environment (backend/.env)
```env
PORT=5000
NODE_ENV=development

# Supabase
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_KEY=your_supabase_service_key

# OpenAI
OPENAI_API_KEY=sk-your_openai_api_key

# Weather API
OPENWEATHER_API_KEY=your_openweather_api_key

# JWT
JWT_SECRET=your_super_secret_jwt_key_here_make_it_long_and_random

# Optional APIs
WHATSAPP_TOKEN=your_whatsapp_token
GOOGLE_TRANSLATE_API_KEY=your_google_translate_api_key
```

#### Frontend Environment (.env)
```env
VITE_API_URL=http://localhost:5000/api
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
```

### 5. Start the Application

#### Terminal 1 - Backend
```bash
cd backend
npm run dev
```

#### Terminal 2 - Frontend
```bash
npm run dev
```

### 6. Test the Setup

1. Open http://localhost:5173
2. Try the AI Advisory feature
3. Test weather data
4. Upload an image for disease detection
5. Check market prices

## 🔧 Configuration Details

### Database Schema
The database includes tables for:
- User profiles and authentication
- AI conversation history
- Image analysis results
- Market price data
- Weather alerts
- Community posts
- Government schemes

### API Integration
- **AI Services**: OpenAI GPT-4 Vision for image analysis, GPT-3.5 for advice
- **Weather**: OpenWeatherMap for current weather and forecasts
- **Authentication**: Supabase Auth with JWT tokens
- **File Storage**: Local storage with Sharp image processing

### Security Features
- Row Level Security (RLS) in Supabase
- JWT authentication
- Rate limiting (100 requests/15min)
- CORS protection
- File upload validation
- Input sanitization

## 🌐 Production Deployment

### Backend Deployment (Railway/Render)
1. Connect your GitHub repository
2. Set environment variables in dashboard
3. Deploy backend service
4. Update frontend VITE_API_URL

### Frontend Deployment (Vercel/Netlify)
1. Connect GitHub repository
2. Set build command: `npm run build`
3. Set environment variables
4. Deploy

### Database Migration
1. Export data from development
2. Run schema on production database
3. Import data if needed

## 🔍 Troubleshooting

### Common Issues

#### Backend won't start
- Check if all environment variables are set
- Verify API keys are valid
- Ensure port 5000 is available

#### Frontend can't connect to backend
- Check VITE_API_URL in frontend .env
- Verify backend is running on correct port
- Check CORS settings in backend

#### AI features not working
- Verify OpenAI API key is valid
- Check if you have sufficient credits
- Ensure proper model access (GPT-4 Vision)

#### Weather data not loading
- Verify OpenWeatherMap API key
- Check if API key has proper permissions
- Ensure location coordinates are valid

#### Image upload failing
- Check file size (max 10MB)
- Verify image format (JPEG, PNG)
- Ensure uploads directory exists

### Debug Commands
```bash
# Check backend logs
cd backend && npm run dev

# Test API endpoints
curl http://localhost:5000/api/health

# Check database connection
# Use Supabase dashboard SQL editor
```

## 📱 Mobile Features

### Voice Recognition
- Requires HTTPS in production
- Needs microphone permissions
- Supports 12+ Indian languages

### Camera Integration
- Requires camera permissions
- Works on mobile browsers
- Automatic disease detection

### Offline Support
- Service worker for caching
- Offline data storage
- Sync when online

## 🔐 Security Checklist

- [ ] All API keys are in environment variables
- [ ] Database has Row Level Security enabled
- [ ] Rate limiting is configured
- [ ] CORS is properly set up
- [ ] File uploads are validated
- [ ] JWT secrets are secure
- [ ] HTTPS is enabled in production

## 📊 Monitoring & Analytics

### Error Tracking
- Implement Sentry for error monitoring
- Set up log aggregation
- Monitor API response times

### Usage Analytics
- Track feature usage
- Monitor user engagement
- Analyze popular queries

### Performance Monitoring
- Database query optimization
- API response time tracking
- Image processing performance

## 🤝 Contributing

1. Fork the repository
2. Create feature branch
3. Make changes
4. Test thoroughly
5. Submit pull request

## 📞 Support

### Documentation
- API documentation in backend/README.md
- Frontend components documentation
- Database schema documentation

### Community
- GitHub Issues for bugs
- Discussions for feature requests
- Wiki for additional guides

### Contact
- Email: support@digitalkrishi.com
- Phone: 1800-180-1551 (Kisan Helpline)
- WhatsApp: +91-XXXXXXXXXX

## 🎯 Next Steps

After setup, consider:
1. Adding more crop varieties
2. Integrating additional weather sources
3. Implementing push notifications
4. Adding multilingual content
5. Creating mobile app versions
6. Integrating with government APIs
7. Adding e-commerce features
8. Implementing IoT sensor integration

## 📈 Scaling Considerations

### Performance
- Implement Redis caching
- Use CDN for static assets
- Optimize database queries
- Add load balancing

### Features
- Real-time chat support
- Video consultations
- Marketplace integration
- IoT device connectivity
- Blockchain for supply chain

### Infrastructure
- Microservices architecture
- Container deployment
- Auto-scaling setup
- Multi-region deployment