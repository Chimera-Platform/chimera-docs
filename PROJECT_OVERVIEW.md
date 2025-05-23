# Project Overview

A modern full-stack AI-powered chat application built with Next.js frontend and Go backend, featuring real-time messaging, Firebase integration, and AI capabilities.

## 🏗️ Architecture

```
┌─────────────────┐    HTTP/REST     ┌─────────────────┐
│                 │  ──────────────▶ │                 │
│  Next.js        │                  │  Go Backend     │
│  Frontend       │  ◀────────────── │  (Gin)          │
│                 │                  │                 │
└─────────────────┘                  └─────────────────┘
         │                                     │
         │                                     │
         ▼                                     ▼
┌─────────────────┐                  ┌─────────────────┐
│                 │                  │                 │
│  Firebase       │                  │  External APIs  │
│  Services       │                  │                 │
│  • Auth         │                  │  • OpenRouter   │
│  • Firestore    │                  │  • Replicate    │
│  • Storage      │                  │                 │
└─────────────────┘                  └─────────────────┘
```

## 📚 Repository Structure

This project is split into two main repositories:

### Frontend Repository
- **Technology**: Next.js 14 with React 18
- **Styling**: Tailwind CSS + Radix UI components
- **Authentication**: Firebase Auth client-side
- **State Management**: React Context + Custom hooks
- **Real-time**: Firebase Firestore real-time listeners

### Backend Repository  
- **Technology**: Go 1.23+ with Gin framework
- **Authentication**: Firebase Admin SDK for token verification
- **Database**: Firebase Firestore
- **Storage**: Firebase Storage for file uploads
- **AI Integration**: OpenRouter and Replicate APIs
- **Containerization**: Docker support

## 🚀 Key Features

### User Management
- **Registration/Login**: Firebase Authentication
- **Profile Management**: User profiles with avatars
- **Session Management**: JWT token-based authentication

### Chat System
- **Real-time Messaging**: Live chat with Firebase Firestore
- **Conversation Management**: Multiple chat conversations
- **Message History**: Persistent message storage
- **File Sharing**: Upload and share images/files

### AI Integration
- **AI Chat**: Conversations with AI models via OpenRouter
- **Content Generation**: AI-powered content generation
- **Multiple Models**: Support for different AI models

### User Interface
- **Responsive Design**: Mobile-first responsive layout
- **Dark/Light Mode**: Theme switching capability
- **Modern UI**: Clean, professional interface with animations
- **Accessibility**: WCAG compliant with Radix UI components

## 🔄 Data Flow

### Authentication Flow
1. User registers/logs in via Frontend
2. Firebase returns ID token
3. Frontend stores token and sends to Backend
4. Backend verifies token with Firebase Admin SDK
5. Backend returns user data or protected resources

### Chat Flow
1. Frontend sends message via Backend API
2. Backend validates user and stores in Firestore
3. Firestore triggers real-time updates
4. Frontend receives real-time updates via Firestore listeners

### AI Integration Flow
1. User sends message to AI via Frontend
2. Frontend sends request to Backend API
3. Backend forwards request to AI service (OpenRouter/Replicate)
4. AI response sent back through Backend to Frontend
5. Conversation stored in Firestore for history

## 🛠️ Technology Stack

### Frontend Technologies
| Category | Technology | Purpose |
|----------|------------|---------|
| Framework | Next.js 14 | React framework with SSR/SSG |
| Language | TypeScript/JavaScript | Type-safe development |
| Styling | Tailwind CSS | Utility-first CSS framework |
| UI Components | Radix UI | Accessible component library |
| Icons | Lucide React, Heroicons | Icon libraries |
| Animation | Framer Motion | Animation library |
| Authentication | Firebase Auth | User authentication |
| Database | Firebase Firestore | Real-time database |
| HTTP Client | Axios | API communication |
| Markdown | React Markdown | Markdown rendering |

### Backend Technologies
| Category | Technology | Purpose |
|----------|------------|---------|
| Language | Go 1.23+ | High-performance backend language |
| Framework | Gin | Fast HTTP web framework |
| Authentication | Firebase Admin SDK | Token verification |
| Database | Firebase Firestore | Document database |
| Storage | Firebase Storage | File storage |
| AI APIs | OpenRouter, Replicate | AI model integration |
| Environment | godotenv | Environment configuration |
| Containerization | Docker | Container deployment |

## 🔐 Security Considerations

### Authentication Security
- Firebase ID tokens for secure authentication
- Token verification on backend with Admin SDK
- Automatic token refresh handling
- Protected routes with middleware

### Data Security
- Environment variables for sensitive data
- Service account keys stored securely
- CORS configuration for API access
- Input validation and sanitization

### API Security
- Rate limiting (recommended for production)
- Request validation middleware
- Error handling without information leakage
- HTTPS enforcement (production)

## 🚀 Development Setup

### Prerequisites
- Node.js 18+
- Go 1.23+
- Firebase project
- AI service API keys (optional)

### Quick Start
1. **Clone both repositories**
2. **Set up Firebase project** with Auth, Firestore, and Storage
3. **Configure environment variables** in both frontend and backend
4. **Install dependencies** for both projects
5. **Start backend server** (port 8080)
6. **Start frontend development** (port 3000)

### Development Workflow
1. Backend changes require Go restart
2. Frontend has hot reload for instant updates
3. Database changes reflect in real-time
4. Environment variables need restart

## 📦 Deployment

### Recommended Deployment Strategy

#### Frontend Deployment
- **Vercel** (Recommended - Next.js native)
- **Netlify** 
- **AWS Amplify**
- **Google Cloud Run**

#### Backend Deployment
- **Google Cloud Run** (Recommended - Firebase integration)
- **AWS ECS/Lambda**
- **DigitalOcean App Platform**
- **Railway**

### Environment Configuration
- Use platform environment variable settings
- Never commit credentials to repositories
- Use secure secret management
- Configure CORS for production domains

## 🔧 Configuration

### Frontend Configuration
- Firebase client configuration
- API endpoint configuration
- Theme and UI settings
- Build and deployment settings

### Backend Configuration  
- Firebase Admin SDK setup
- Database connection settings
- AI service API configurations
- Server and middleware settings

## 📊 Monitoring & Analytics

### Recommended Tools
- **Frontend**: Vercel Analytics, Google Analytics
- **Backend**: Application logs, Firebase monitoring
- **Database**: Firebase console monitoring
- **Performance**: Web vitals, API response times

## 🤝 Contributing

### Development Process
1. Fork the appropriate repository
2. Create feature branches
3. Follow code style guidelines
4. Write tests for new features
5. Submit pull requests

### Code Standards
- **Frontend**: ESLint + Prettier configuration
- **Backend**: Go formatting with gofmt
- **Commits**: Conventional commit messages
- **Documentation**: Update READMEs for changes

## 📄 License

This project is licensed under the MIT License. See LICENSE files in individual repositories for details.

## 🔗 Related Repositories

- **Frontend Repository**: [Link to frontend repo]
- **Backend Repository**: [Link to backend repo]
- **Documentation**: [Link to docs repo if separate]

## 📞 Support

For issues and questions:
- Check individual repository issues
- Create detailed bug reports
- Include reproduction steps
- Provide environment information 