# Cliqtrix 2025 - Intelligent Multi-Agent Tours & Holidays Chatbot System

## 🎯 Project Overview

Cliqtrix is an **advanced AI-powered multi-agent chatbot system** designed for the Tours & Holidays industry. It demonstrates sophisticated AI agent capabilities by implementing a distributed agent architecture where multiple specialized agents collaborate to handle complex travel booking workflows.

**Problem Statement:** Travel businesses struggle to automate customer engagement, package discovery, and booking management. Manual processes are time-consuming and error-prone, resulting in lost leads and poor customer experience.

**Solution:** A multi-agent AI system where intelligent agents work together to:
- Understand customer travel preferences through conversational AI
- Recommend personalized travel packages
- Manage complex booking workflows
- Handle real-time inventory and payment processing
- Provide customer support 24/7

## 🤖 AI Agent Architecture & Key Concepts Implemented

This project demonstrates **3+ core concepts** from modern AI agent design:

### 1. **Multi-Agent System** ✓
- **Concierge Agent** (LLM-powered) - Handles natural language conversations, user intent recognition
- **Package Recommendation Agent** - Specialized agent for package matching and recommendations
- **Booking Management Agent** - Handles booking workflows and state management
- **Payment Processing Agent** - Manages payment and transaction verification
- **Customer Support Agent** - Resolves queries and issues

These agents work in **parallel and sequential** patterns:
- **Parallel**: Multiple agents process different user requests simultaneously
- **Sequential**: Agents hand off information in workflow sequences (e.g., Recommendation Agent → Booking Agent → Payment Agent)

### 2. **Tools & Interoperability** ✓
- **Custom Tools**:
  - Package Search Tool - Query travel packages by destination, budget, duration
  - CRM Tool - Access Zoho CRM for lead management
  - Payment Gateway Tool - Process transactions
  - Email Tool - Send confirmations and receipts
- **External APIs**: 
  - Zoho SalesIQ Platform integration
  - Third-party travel package APIs
  - Payment processing APIs
- **Long-running Operations**: Async booking requests with status tracking

### 3. **Sessions & Memory Management** ✓
- **Session Management** - Maintains user conversation context across multiple interactions
- **Short-term Memory** - Current conversation state and user preferences
- **Long-term Memory** - User booking history, preferences, saved packages
- **InMemorySessionService** - Efficient state management for real-time interactions
- **Memory Bank** - Persistent storage of user travel history and preferences

### 4. **Context Engineering** ✓
- Dynamic prompt engineering based on user context
- Context compaction for efficient token usage
- Maintains conversation history for coherent responses

### 5. **Observability & Logging** ✓
- Comprehensive logging of agent decisions and actions
- Tracing agent workflows through complex booking processes
- Metrics tracking for agent performance (response time, success rate, user satisfaction)

## 🏗️ Technical Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    User Interface Layer                      │
│            (HTML5/CSS3/JavaScript Frontend)                 │
│         Zoho SalesIQ Widget Integration                      │
└──────────────────────┬──────────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────────┐
│              Agent Orchestration Layer                       │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │   Concierge  │  │ Recommendation│  │   Booking    │      │
│  │    Agent     │  │     Agent     │  │    Agent     │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
│        │                   │                  │              │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │   Payment    │  │   Support    │  │   Context    │      │
│  │    Agent     │  │     Agent     │  │    Engine    │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
└──────────────────────┬──────────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────────┐
│              Backend Service Layer                          │
│         (Deluge Scripts - Zoho Platform)                    │
│  - REST API Endpoints                                       │
│  - Business Logic Processing                               │
│  - External API Integration                                │
└──────────────────────┬──────────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────────┐
│              Data Layer                                      │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │   MongoDB    │  │   Zoho CRM   │  │    Cache     │      │
│  │   Database   │  │ Integration  │  │   Storage    │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
└──────────────────────────────────────────────────────────────┘
```

## 📦 Tech Stack

### Frontend
- HTML5, CSS3, JavaScript ES6+
- Zoho SalesIQ Widget Integration
- Responsive Chat Interface

### Backend
- **Deluge** (Zoho's server-side scripting language for agent logic)
- **Zoho SalesIQ** Platform (AI agent framework)
- REST APIs

### Database
- **MongoDB** - NoSQL database for:
  - Travel packages catalog
  - User leads and preferences
  - Booking records
  - Session data

### Integrations
- Zoho SalesIQ (Core agent platform)
- Zoho CRM (Lead management)
- Payment Gateways
- Third-party travel APIs

## 🚀 Key Features

### Intelligent Agent Features
1. **Natural Language Understanding** - Agents understand travel preferences conversationally
2. **Multi-turn Conversations** - Maintain context across multiple user interactions
3. **Preference Learning** - Agents learn user preferences over time
4. **Real-time Decision Making** - Agents make intelligent routing and recommendation decisions
5. **Autonomous Task Execution** - Agents handle booking steps without human intervention
6. **Adaptive Responses** - Tailored responses based on user profile and context
7. **Error Recovery** - Graceful handling and recovery from failures

### Booking System
1. **Featured Packages** - Display top travel packages
2. **Intelligent Search** - Find packages matching user preferences
3. **Booking Management** - Complete end-to-end booking process
4. **Payment Processing** - Secure transaction handling
5. **Invoice Generation** - Automated invoice creation
6. **OTP Verification** - Secure verification system
7. **Booking History** - Track user bookings and preferences

## 📋 Installation & Setup

### Prerequisites
- Zoho Account with SalesIQ activated
- MongoDB instance (local or Atlas)
- Node.js 14+ (for local development)
- Git
- API keys for payment gateway and travel data services

### Quick Start

```bash
# Clone repository
git clone https://github.com/selva18052005/Cliqtrix-Tours-Holiday-Bot.git
cd Cliqtrix-Tours-Holiday-Bot

# Install dependencies
npm install

# Configure environment variables
cp .env.example .env
# Edit .env with your Zoho credentials, MongoDB URI, API keys

# Initialize MongoDB
npm run db:init

# Deploy to Zoho SalesIQ
npm run deploy:zoho
```

### Deployment

1. **Frontend Deployment**
   - Upload HTML/CSS/JS files to Zoho SalesIQ
   - Configure widget in SalesIQ console

2. **Backend Deployment**
   - Deploy Deluge scripts to Zoho platform
   - Configure webhooks and API endpoints
   - Set environment variables

3. **Database Setup**
   - Create MongoDB collections
   - Index key fields for performance
   - Set up data retention policies

## 🔌 API Endpoints

### Agent Operations
```
POST   /api/chat/message           - Send message to agent
GET    /api/chat/context           - Get conversation context
POST   /api/packages/search        - Search for packages
POST   /api/recommendations        - Get personalized recommendations
POST   /api/bookings/create        - Create new booking
GET    /api/bookings/status/:id    - Track booking status
POST   /api/payment/process        - Process payment
GET    /api/user/history           - Get user booking history
```

## 🗄️ Database Schema

### Collections

**Packages**
```json
{
  "_id": "ObjectId",
  "name": "string",
  "destination": "string",
  "duration": "number",
  "budget": "number",
  "description": "string",
  "itinerary": ["array"],
  "features": ["array"],
  "rating": "number",
  "availability": "boolean"
}
```

**Users (Long-term Memory)**
```json
{
  "_id": "ObjectId",
  "email": "string",
  "phone": "string",
  "preferences": {
    "favoriteDestinations": ["array"],
    "budgetRange": "object",
    "travelStyle": "string"
  },
  "bookingHistory": ["array"],
  "savedPackages": ["array"],
  "createdAt": "date"
}
```

**Bookings**
```json
{
  "_id": "ObjectId",
  "userId": "ObjectId",
  "packageId": "ObjectId",
  "status": "enum",
  "amount": "number",
  "paymentId": "string",
  "invoiceId": "string",
  "createdAt": "date",
  "bookedAt": "date"
}
```

## 📊 Agent Evaluation Metrics

- **Conversation Success Rate** - % of successful bookings initiated
- **User Satisfaction** - Post-interaction ratings
- **Response Time** - Average agent response latency
- **Recommendation Accuracy** - % of accepted recommendations
- **Error Rate** - Failed operations and recovery success
- **Concurrency** - Number of simultaneous conversations handled

## 🎓 Learning Outcomes from AI Agents Intensive Course

This project demonstrates practical application of:
1. Multi-agent architectures and orchestration
2. Tool design and API integration
3. Context and memory management systems
4. Agent evaluation and monitoring
5. Handling long-running async operations
6. Real-world production agent deployment
7. Agent collaboration patterns (sequential and parallel)

## 📄 License

MIT License - See LICENSE file for details

## 👤 Author

**Kabilan Baskar**  
Built as part of Kaggle's AI Agents Intensive Course with Google  
Submitted to Kaggle Freestyle AI Agents Competition  
December 2025

## 📞 Contact

For questions about this project:
- GitHub: [@selva18052005](https://github.com/selva18052005)
- Email: kabilanbaskar267@gmail.com

## 🙏 Acknowledgments

- Google & Kaggle for the AI Agents Intensive Course
- Zoho Corporation for SalesIQ platform
- MongoDB for database technology
- All contributors and reviewers
