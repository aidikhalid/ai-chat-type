# AI Chat Type

A full-stack AI-powered chat application built with React, Express, and OpenAI's GPT-4o-mini.

## 🌐 Live Demo

Check out the live application: [https://ai-chat-type.aidikhalid.com/](https://ai-chat-type.aidikhalid.com/)

## Features

- 🤖 **AI Chat Interface** - Real-time conversations with OpenAI GPT-4o-mini
- 🔐 **Authentication** - Secure JWT-based auth with HTTP-only cookies
- 🛡️ **Security** - Arcjet integration (rate limiting, bot detection, shield protection)
- 🎨 **Modern UI** - Radix UI components with dark/light theme support
- ⚡ **Optimistic Updates** - Instant UI feedback with React Query
- 📱 **Responsive Design** - Mobile-first design with Tailwind CSS v4
- 💾 **Persistent Chat History** - MongoDB storage for all conversations

## Tech Stack

### Frontend

- **React 19** with TypeScript
- **React Query** for server state management
- **React Router** for navigation
- **Radix UI** for accessible components
- **Tailwind CSS v4** for styling
- **Vite** for build tooling

### Backend

- **Express.js** with TypeScript
- **MongoDB** with Mongoose
- **OpenAI API** (GPT-4o-mini)
- **JWT** for authentication
- **Arcjet** for security (rate limiting, bot detection)
- **bcrypt** for password hashing

## Prerequisites

- Node.js 18+ and npm
- MongoDB (local or Atlas)
- OpenAI API key
- Arcjet account (optional, for security features)

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/aidikhalid/ai-chat-type.git
cd ai-chat-type
```

### 2. Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file in the backend directory:

```env
PORT=3000
NODE_ENV=development
MONGODB_URL=mongodb://localhost:27017/ai-chat-type
JWT_SECRET=your-super-secret-jwt-key
COOKIE_SECRET=your-super-secret-cookie-key
OPENAI_API_KEY=sk-your-openai-api-key
ARCJET_KEY=your-arcjet-key
CLIENT_URL=http://localhost:5173
```

### 3. Frontend Setup

```bash
cd ../frontend
npm install
```

## Running the Application

### Start Backend (from backend directory)

```bash
npm run dev
```

Server runs on http://localhost:3000

### Start Frontend (from frontend directory)

```bash
npm run dev
```

Frontend runs on http://localhost:5173

## Default Credentials (Development)

After running the database reset endpoint:

- **Email**: shinji@nerv.com
- **Password**: 123456

## Project Structure

```
ai-chat-type/
├── backend/
│   ├── src/
│   │   ├── controllers/     # Request handlers
│   │   ├── middleware/      # Auth, Arcjet protection
│   │   ├── models/          # MongoDB schemas
│   │   ├── routes/          # API routes
│   │   ├── utils/           # Helpers, validators
│   │   ├── config/          # OpenAI config
│   │   ├── db/              # Database connection
│   │   ├── app.ts           # Express app setup
│   │   └── index.ts         # Entry point
│   └── package.json
│
├── frontend/
│   ├── src/
│   │   ├── api/             # API client functions
│   │   ├── components/      # React components
│   │   ├── context/         # Auth context
│   │   ├── lib/             # Axios instance
│   │   ├── pages/           # Route pages
│   │   ├── App.tsx          # Main app component
│   │   └── main.tsx         # Entry point
│   └── package.json
│
└── README.md
```

## API Endpoints

### Authentication

- `POST /api/v1/auth/signup` - Register new user
- `POST /api/v1/auth/login` - Login user
- `GET /api/v1/auth/logout` - Logout user
- `GET /api/v1/auth/verify` - Verify JWT token

### Chats

- `GET /api/v1/chats` - Get user's chat history
- `POST /api/v1/chats` - Send message and get AI response
- `DELETE /api/v1/chats` - Clear chat history

### Database (Development Only)

- `POST /api/v1/database/reset` - Reset database to default state

## Security Features

- **JWT Authentication** with HTTP-only signed cookies
- **Arcjet Protection**:
  - Token bucket rate limiting (10 requests per 10 seconds)
  - Bot detection and blocking
  - Shield protection against common attacks
- **Password Hashing** with bcrypt (10 rounds)
- **Input Validation** with express-validator
- **CORS** configured for specific origin

## Building for Production

### Backend

```bash
cd backend
npm run build
npm start
```

### Frontend

```bash
cd frontend
npm run build
npm run preview
```

## Environment Variables

See `.env.example` files in both backend and frontend directories for required environment variables.

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is open source and available under the MIT License.

## Author

**Aidi Khalid**

- GitHub: [@aidikhalid](https://github.com/aidikhalid)
- LinkedIn: [Aidi Khalid](https://www.linkedin.com/in/aidikhalid)

## Acknowledgments

- OpenAI for GPT-4o-mini API
- Radix UI for accessible components
- Arcjet for security features
