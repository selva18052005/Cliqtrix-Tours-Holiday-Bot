# Cliqtrix 2025 - Tours & Holidays SalesIQ Chatbot

## Project Overview

This is a comprehensive SalesIQ Chatbot application for the Tours & Holidays industry, built as part of the Cliqtrix 2025 contest by Zoho. The application enables travel businesses to engage website visitors through an intelligent chatbot that handles package inquiries, bookings, and customer support.

## Tech Stack

### Frontend
- HTML5, CSS3, JavaScript (ES6+)
- SalesIQ Widget Integration
- Responsive Design

### Backend
- **Deluge** (Zoho's scripting language)
- **Zoho SalesIQ** Platform
- REST APIs

### Database
- **MongoDB** - NoSQL database for storing packages, leads, and bookings
- Connection via Mongoose ODM

### Integration
- Zoho SalesIQ Platform
- Zoho CRM (for lead management)
- Third-party APIs (for package data)

## Project Structure

```
Cliqtrix-Tours-Holiday-Bot/
├── frontend/
│   ├── index.html           # Main chat interface
│   ├── styles/
│   │   └── style.css        # Styling for bot UI
│   └── js/
│       ├── chatbot.js       # Chat logic
│       ├── api.js           # API calls
│       └── utils.js         # Utility functions
├── backend/
│   ├── deluge/
│   │   ├── handlers.deluge  # Deluge functions for bot logic
│   │   ├── api.deluge       # API endpoints
│   │   └── database.deluge  # MongoDB operations
│   └── config/
│       └── zoho-config.json # Zoho platform config
├── database/
│   ├── schemas/
│   │   ├── package.schema.js
│   │   ├── lead.schema.js
│   │   └── booking.schema.js
│   └── mongodb-init.js      # MongoDB initialization
├── docs/
│   ├── SETUP.md             # Setup instructions
│   ├── API_DOCS.md          # API documentation
│   └── DEPLOYMENT.md        # Deployment guide
├── .gitignore
├── package.json
└── README.md
```

## Features

### Chatbot Features
1. **Featured Packages** - Display tour packages from CRM/database
2. **Find a Package** - Search and recommend packages based on user preferences
3. **My Packages** - View previously booked packages
4. **Lead Management** - Capture visitor information
5. **Booking System** - Complete booking process with invoice generation
6. **Payment Integration** - Support for payment processing
7. **OTP Verification** - Phone number verification
8. **OAuth 2.0 Authentication** - Secure third-party integration
9. **AI Integration** - AI-powered recommendations (optional)

## Installation

### Prerequisites
- Zoho Account with SalesIQ
- MongoDB instance (local or cloud)
- Node.js (for development)
- Git

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/selva18052005/Cliqtrix-Tours-Holiday-Bot.git
   cd Cliqtrix-Tours-Holiday-Bot
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure MongoDB**
   - Update `database/mongodb-init.js` with your MongoDB connection string
   - Run migrations: `npm run db:init`

4. **Deploy to Zoho SalesIQ**
   - Upload frontend files to SalesIQ
   - Deploy Deluge functions via Zoho platform
   - Configure webhooks and APIs

## API Endpoints

### Bot Operations
- `POST /api/chat/message` - Send chat message
- `GET /api/packages` - Get available packages
- `GET /api/packages/search` - Search packages
- `POST /api/leads` - Create lead
- `POST /api/bookings` - Create booking
- `GET /api/bookings/:leadId` - Get lead bookings

## Database Schemas

### Packages
```json
{
  "name": "string",
  "destination": "string",
  "duration": "number",
  "budget": "number",
  "description": "string",
  "itinerary": "array",
  "features": "array"
}
```

### Leads
```json
{
  "name": "string",
  "email": "string",
  "phone": "string",
  "preferences": "object",
  "createdAt": "date",
  "source": "string"
}
```

### Bookings
```json
{
  "leadId": "ObjectId",
  "packageId": "ObjectId",
  "status": "string",
  "amount": "number",
  "invoiceId": "string",
  "bookedAt": "date"
}
```

## Deployment

### Deploy to Zoho Platform

1. Package the application
2. Upload to Zoho SalesIQ
3. Configure webhook URLs
4. Set environment variables
5. Test all functionalities

See `docs/DEPLOYMENT.md` for detailed instructions.

## Contributing

This is a contest entry. For any improvements, please create a branch and submit for review.

## License

This project is licensed under the MIT License - see LICENSE file for details.

## Contact

For queries, visit [Cliqtrix Official](https://cliqtrix.com) or contact `contact@cliqtrix.com`

## Acknowledgments

- Zoho Corporation for Cliqtrix 2025 contest
- Zoho SalesIQ platform team
- MongoDB community
