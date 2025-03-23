# ShutleFY(Full Stack Authentication System with Booking Features)

A comprehensive full-stack application featuring robust authentication, user management, and booking capabilities. Built with modern technologies and best practices.

![WhatsApp Image 2025-03-23 at 17 00 59_f4d8dd1b](https://github.com/user-attachments/assets/117b2dca-6d75-4d0b-94d9-350dd485cf2c)
![WhatsApp Image 2025-03-23 at 17 01 00_a6b4896c](https://github.com/user-attachments/assets/c747ca36-5cfb-4cc7-801c-7a5106b9a0c6)
![WhatsApp Image 2025-03-23 at 17 01 04_3935ca14](https://github.com/user-attachments/assets/c8791432-bae6-4eeb-b064-782e9c97c6ec)
![WhatsApp Image 2025-03-23 at 17 01 04_b29527f0](https://github.com/user-attachments/assets/44224c73-d91f-4989-b675-4d59260b9540)
![WhatsApp Image 2025-03-23 at 17 01 01_c2555c91](https://github.com/user-attachments/assets/4acdc53a-4445-41c2-a740-577eaefe7882)
![WhatsApp Image 2025-03-23 at 17 01 03_fc080354](https://github.com/user-attachments/assets/a1e6affa-3546-4816-9c0b-6fffeb1a7bbd)


## 🌟 Features

### Authentication & Security
- JWT-based authentication
- Google OAuth integration
- Email verification via OTP
- Password reset functionality
- Role-based access control (User, Admin, Prime Admin)
- Secure password handling with bcrypt
- Protected routes and API endpoints

### User Management
- User registration and profile management
- Email verification system
- Password reset with OTP verification
- User role management
- Profile settings and preferences

### Booking System
- Interactive booking interface
- Real-time booking management
- Trip history tracking
- Wallet integration
- Payment processing (PayPal integration)
- Location-based services with maps (Leaflet integration)

### Admin Features
- Admin dashboard
- User management
- Booking oversight
- System monitoring
- Analytics and reporting

### Performance & Caching
- Redis-based caching system
- API response caching
- User session caching
- Rate limiting with Redis
- Cache invalidation strategies
- Distributed caching support
- Cache warming mechanisms
- Real-time cache updates

## 🏗️ Project Structure

```
├── auth-backend/                 # Backend server
│   ├── src/
│   │   ├── config/             # Configuration files
│   │   ├── controllers/        # Request handlers
│   │   ├── middleware/         # Custom middleware
│   │   ├── migrations/         # Database migrations
│   │   ├── models/             # Database models
│   │   ├── routes/             # API routes
│   │   ├── scripts/            # Utility scripts
│   │   ├── services/           # Business logic
│   │   ├── utils/              # Helper functions
│   │   └── index.ts            # Application entry point
│   ├── .env                    # Environment variables
│   ├── package.json            # Dependencies and scripts
│   └── tsconfig.json           # TypeScript configuration
│
└── front-end/                   # Frontend application
    ├── src/
    │   ├── assets/            # Static assets
    │   ├── components/        # Reusable components
    │   ├── pages/             # Page components
    │   ├── utils/             # Utility functions
    │   ├── App.tsx            # Main application component
    │   └── main.tsx           # Application entry point
    ├── public/                # Public assets
    ├── package.json           # Dependencies and scripts
    └── vite.config.ts         # Vite configuration
```

## 🛠️ Tech Stack

### Backend
- Node.js & Express.js
- TypeScript
- Sequelize ORM with SQLite
- Passport.js for authentication
- JWT for token management
- Nodemailer for email delivery
- Speakeasy for OTP generation
- Redis for caching and rate limiting
- Bull for job queues and background tasks

### Frontend
- React with TypeScript
- Vite for build tooling
- Tailwind CSS for styling
- Framer Motion for animations
- React Router for navigation
- Firebase integration
- PayPal payment integration
- Leaflet for maps
- Recharts for data visualization

## 🚀 Getting Started

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn package manager
- Git

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/auth.git
cd auth
```

2. Set up the backend:
```bash
cd auth-backend
npm install
cp .env.example .env
# Update .env with your configuration
npm run build
npm start
```

3. Set up the frontend:
```bash
cd ../front-end
npm install
npm run dev
```

### Environment Configuration

#### Backend (.env)
```
# Server Configuration
PORT=8000
NODE_ENV=development

# Database Configuration
DB_HOST=localhost
DB_PORT=3306
DB_NAME=auth_db
DB_USER=root
DB_PASSWORD=password

# Redis Configuration
REDIS_HOST=localhost
REDIS_PORT=6379
REDIS_PASSWORD=your_redis_password
REDIS_DB=0

# Cache Configuration
CACHE_TTL=3600
CACHE_PREFIX=auth_app
RATE_LIMIT_WINDOW=15
RATE_LIMIT_MAX_REQUESTS=100

# JWT Configuration
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRATION=86400

# Google OAuth Configuration
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
GOOGLE_CALLBACK_URL=http://localhost:8000/api/auth/google/callback

# Email Configuration
EMAIL_SERVICE=gmail
EMAIL_USER=your_email@gmail.com
EMAIL_PASSWORD=your_email_password
EMAIL_FROM=your_email@gmail.com

# OTP Configuration
OTP_SECRET=your_otp_secret_key
OTP_EXPIRATION=300
```

#### Frontend (.env)
```
VITE_API_URL=http://localhost:8000
VITE_FIREBASE_CONFIG=your_firebase_config
VITE_PAYPAL_CLIENT_ID=your_paypal_client_id
```

## 📚 API Documentation

### Authentication Endpoints
- `POST /api/auth/register` - Register new user
- `POST /api/auth/verify-email` - Verify email with OTP
- `POST /api/auth/resend-otp` - Resend verification OTP
- `POST /api/auth/login` - User login
- `GET /api/auth/google` - Google OAuth login
- `GET /api/auth/google/callback` - Google OAuth callback
- `POST /api/auth/forgot-password` - Request password reset
- `POST /api/auth/reset-password` - Reset password with OTP

### User Management
- `GET /api/users/profile` - Get user profile
- `PUT /api/users/profile` - Update user profile
- `PUT /api/users/change-password` - Change password

### Booking System
- `POST /api/bookings` - Create new booking
- `GET /api/bookings` - Get user bookings
- `GET /api/bookings/:id` - Get booking details
- `PUT /api/bookings/:id` - Update booking
- `DELETE /api/bookings/:id` - Cancel booking

### Admin Endpoints
- `GET /api/admin/users` - Get all users
- `GET /api/admin/bookings` - Get all bookings
- `PUT /api/admin/users/:id` - Update user role
- `GET /api/admin/analytics` - Get system analytics

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

- Your Name - Initial work

## 🙏 Acknowledgments

- React team for the amazing framework
- Express.js team for the backend framework
- All contributors and maintainers of the used libraries 
