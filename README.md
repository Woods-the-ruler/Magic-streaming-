# 🎙️ Magic Streaming - Production Ready Podcast Platform

A professional, scalable podcast streaming platform with AI-powered script generation, built with Express.js, MongoDB, and modern security practices.

## ✨ Features

- **User Authentication**: JWT-based secure authentication
- **Podcast Management**: Upload, delete, and organize podcasts
- **Social Features**: Likes, comments, and follower system
- **AI Script Generation**: Automatic podcast script generation from topics
- **Search & Discovery**: Full-text search with ranking
- **File Validation**: Audio format validation with size limits
- **Production Security**: Helmet, rate limiting, input validation
- **Pagination**: Efficient data retrieval with pagination
- **User Permissions**: Role-based access control

## 🚀 Quick Start

### Prerequisites

- Node.js 18+
- MongoDB (local or Atlas)

### Installation

```bash
# Clone the repository
git clone https://github.com/Woods-the-ruler/Magic-streaming-.git
cd Magic-streaming-

# Install dependencies
npm install

# Create environment file
cp .env.example .env

# Update .env with your MongoDB URI and JWT secret
```

### Running the Application

```bash
# Development mode (with auto-reload)
npm run dev

# Production mode
npm start
```

The server will start on `http://localhost:3000`

## 📋 API Endpoints

### Authentication

```bash
# Register
POST /api/auth/register
{
  "username": "johndoe",
  "email": "john@example.com",
  "password": "securepassword"
}

# Login
POST /api/auth/login
{
  "email": "john@example.com",
  "password": "securepassword"
}

# Get Current User
GET /api/auth/me
Headers: Authorization: Bearer <token>

# Get User by ID
GET /api/auth/:userId
```

### Podcasts

```bash
# Upload Podcast
POST /api/podcasts/upload
Headers: Authorization: Bearer <token>
Form Data: audio (file), title, description, category, visibility

# Get All Podcasts
GET /api/podcasts?page=1&limit=10

# Get Single Podcast
GET /api/podcasts/:podcastId

# Search Podcasts
GET /api/podcasts/search/query?q=topic

# Like Podcast
POST /api/podcasts/:podcastId/like
Headers: Authorization: Bearer <token>

# Add Comment
POST /api/podcasts/:podcastId/comment
Headers: Authorization: Bearer <token>
{
  "text": "Great podcast!"
}

# Delete Podcast
DELETE /api/podcasts/:podcastId
Headers: Authorization: Bearer <token>
```

### AI Script Generation

```bash
# Generate Script
POST /api/generate
Headers: Authorization: Bearer <token>
{
  "topic": "Artificial Intelligence"
}

# Save Generated Podcast
POST /api/generate/save
Headers: Authorization: Bearer <token>
{
  "title": "AI Podcast",
  "script": "...",
  "description": "...",
  "category": "Technology"
}
```

## 🏗️ Project Structure

```
magic-streaming/
├── server/
│   ├── models/
│   │   ├── User.js           # User schema
│   │   └── Podcast.js        # Podcast schema
│   ├── middleware/
│   │   ├── auth.js           # JWT verification
│   │   └── upload.js         # Multer configuration
│   ├── routes/
│   │   ├── auth.js           # Authentication routes
│   │   ├── podcasts.js       # Podcast CRUD routes
│   │   └── generate.js       # AI generation routes
│   └── server.js             # Main Express app
├── uploads/                  # Audio files directory
├── .env.example              # Environment template
├── package.json              # Dependencies
└── README.md                 # This file
```

## 🔐 Security Features

- ✅ JWT Token Authentication
- ✅ Bcrypt Password Hashing
- ✅ Helmet.js Security Headers
- ✅ Rate Limiting (100 requests/15 min)
- ✅ Input Validation (express-validator)
- ✅ CORS Protection
- ✅ Audio MIME Type Validation
- ✅ File Size Limits (50MB default)
- ✅ Environment-based Configuration

## 📦 Dependencies

```json
{
  "express": "^4.18.2",
  "mongoose": "^7.5.0",
  "bcryptjs": "^2.4.3",
  "jsonwebtoken": "^9.1.0",
  "multer": "^1.4.5-lts.1",
  "cors": "^2.8.5",
  "dotenv": "^16.3.1",
  "express-validator": "^7.0.0",
  "helmet": "^7.0.0",
  "express-rate-limit": "^7.1.5"
}
```

## 🎯 Next Steps

1. **Frontend**: Build React/Vue frontend
2. **Database**: Set up MongoDB Atlas for production
3. **Deployment**: Deploy to AWS, Heroku, or DigitalOcean
4. **Text-to-Speech**: Integrate TTS API for generated podcasts
5. **Storage**: Migrate to S3/Cloud Storage
6. **Analytics**: Add tracking and metrics

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License.

## 📞 Support

For issues and questions, please open an GitHub issue.

---

**Made with ❤️ by the Magic Streaming Team**
