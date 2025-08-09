# Pakistan Islamia Higher Secondary School Sharjah - Document Management System

## 🎓 Project Overview

A comprehensive Document Request & Approval System (DRAS) built specifically for Pakistan Islamia Higher Secondary School Sharjah. This system streamlines the document request process with role-based access control, automated workflows, and professional UI/UX design.

## ✨ Key Features

### 🔐 Authentication & Authorization
- JWT-based authentication with access and refresh tokens
- Role-based access control (Admin, Principal, User)
- Secure password hashing with bcrypt
- Session management and automatic token refresh

### 📋 User Management
- Complete CRUD operations for users
- Role assignment and permission management
- Profile management with avatar support
- Employee ID generation and tracking

### 📄 Document Request System
- Multi-file upload support (PDF, DOC, DOCX)
- Application tracking with unique IDs
- Status management (Pending, Approved, Rejected, Returned)
- Priority levels and urgent marking
- Category-based organization

### 🔍 Review & Approval Workflow
- Principal review dashboard
- Comment system with attachments
- Bulk actions for applications
- Email notifications on status changes
- Application history tracking

### 📊 Analytics & Reporting
- Real-time dashboard statistics
- Application trends and metrics
- User activity monitoring
- System health indicators

### 🎨 Modern UI/UX
- Responsive design with Tailwind CSS
- Dark/Light theme support
- Smooth animations with Framer Motion
- Professional color schemes
- Mobile-first approach

## 🛠 Tech Stack

### Backend
- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MongoDB with Mongoose ODM
- **Authentication**: JWT (JSON Web Tokens)
- **File Upload**: Multer
- **Validation**: Express Validator
- **Security**: Helmet, CORS, Rate Limiting

### Frontend
- **Library**: React.js 18
- **Routing**: React Router DOM
- **State Management**: Context API + React Query
- **Styling**: Tailwind CSS
- **Animations**: Framer Motion
- **Icons**: Lucide React
- **Forms**: React Hook Form
- **Notifications**: React Hot Toast

### Development Tools
- **Package Manager**: npm
- **Code Quality**: ESLint, Prettier
- **Version Control**: Git
- **Environment**: dotenv

## 📦 Installation & Setup

### Prerequisites
- Node.js (v16 or higher)
- MongoDB (running locally or MongoDB Atlas)
- npm or yarn package manager
- Git

### 1. Clone the Repository
```bash
git clone <repository-url>
cd school-document-system
```

### 2. Backend Setup

Navigate to the backend directory:
```bash
cd backend
```

Install dependencies:
```bash
npm install
```

Create environment file:
```bash
cp .env.example .env
```

Configure your environment variables in `.env`:
```env
NODE_ENV=development
PORT=5000
MONGODB_URI=mongodb://localhost:27017/school_document_system
JWT_SECRET=your_jwt_secret_here
JWT_REFRESH_SECRET=your_refresh_secret_here
```

Start the backend server:
```bash
npm run dev
```

The backend will be available at `http://localhost:5000`

### 3. Frontend Setup

Open a new terminal and navigate to the frontend directory:
```bash
cd frontend
```

Install dependencies:
```bash
npm install
```

Start the frontend development server:
```bash
npm start
```

The frontend will be available at `http://localhost:3000`

### 4. Database Initialization

The system will automatically:
- Create the MongoDB database `school_document_system`
- Set up required collections (users, roles, applications, comments)
- Create default roles (admin, principal, user)
- Create default admin user

## 👤 Default User Accounts

### Admin Account
- **Email**: admin@pakistanischoolsharjah.com
- **Password**: Admin@123
- **Role**: Administrator
- **Access**: Full system access

### Demo Accounts (Optional)
You can create additional demo accounts through the registration process or admin panel:

- **Principal**: principal@school.com / Principal@123
- **User**: user@school.com / User@123

## 🗂 Project Structure

```
school-document-system/
├── backend/
│   ├── models/          # Database models
│   ├── routes/          # API routes
│   ├── middleware/      # Custom middleware
│   ├── uploads/         # File uploads directory
│   ├── server.js        # Main server file
│   └── package.json
├── frontend/
│   ├── public/          # Static assets
│   ├── src/
│   │   ├── components/  # Reusable components
│   │   ├── pages/       # Page components
│   │   ├── contexts/    # React contexts
│   │   ├── services/    # API services
│   │   ├── hooks/       # Custom hooks
│   │   └── utils/       # Utility functions
│   └── package.json
└── README.md
```

## 🔄 API Endpoints

### Authentication
- `POST /api/auth/login` - User login
- `POST /api/auth/register` - User registration
- `POST /api/auth/refresh` - Refresh access token
- `POST /api/auth/logout` - User logout
- `GET /api/auth/me` - Get current user profile

### Applications
- `GET /api/applications` - Get user applications
- `POST /api/applications` - Create new application
- `GET /api/applications/:id` - Get application details
- `PUT /api/applications/:id` - Update application
- `DELETE /api/applications/:id` - Delete application

### Principal Routes
- `GET /api/principal/applications` - Get all applications for review
- `POST /api/principal/applications/:id/approve` - Approve application
- `POST /api/principal/applications/:id/reject` - Reject application
- `POST /api/principal/applications/:id/return` - Return for revision

### Admin Routes
- `GET /api/admin/users` - Get all users
- `POST /api/admin/users` - Create new user
- `PUT /api/admin/users/:id` - Update user
- `DELETE /api/admin/users/:id` - Delete user
- `GET /api/admin/dashboard` - Admin dashboard stats

## 🎨 User Interface Features

### Role-Based Dashboards
- **User Dashboard**: Application submission, tracking, and history
- **Principal Dashboard**: Review queue, approval actions, analytics
- **Admin Dashboard**: System management, user control, comprehensive analytics

### Responsive Design
- Mobile-first approach
- Tablet and desktop optimizations
- Touch-friendly interface
- Progressive Web App ready

### Accessibility Features
- ARIA labels and semantic HTML
- Keyboard navigation support
- High contrast mode
- Screen reader compatibility

## 🔧 Configuration Options

### File Upload Settings
- Maximum file size: 10MB per file
- Allowed formats: PDF, DOC, DOCX
- Maximum files per application: 5
- Automatic file type validation

### Security Features
- Rate limiting (100 requests per 15 minutes)
- CORS protection
- XSS prevention
- SQL injection protection
- Secure headers with Helmet

### Email Notifications (Optional)
Configure SMTP settings in `.env` to enable email notifications:
```env
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your-email@gmail.com
SMTP_PASS=your-app-password
```

## 📱 Mobile App Features

The system is designed as a Progressive Web App (PWA) with:
- Offline capability
- Push notifications
- App-like experience
- Home screen installation

## 🔒 Security Best Practices

- Passwords hashed with bcrypt (12 rounds)
- JWT tokens with short expiration
- Refresh token rotation
- Rate limiting on sensitive endpoints
- Input validation and sanitization
- File upload security checks

## 🚀 Deployment

### Backend Deployment
1. Set up MongoDB Atlas or use local MongoDB
2. Configure production environment variables
3. Deploy to services like Heroku, DigitalOcean, or AWS
4. Set up SSL certificates

### Frontend Deployment
1. Build the production version: `npm run build`
2. Deploy to services like Netlify, Vercel, or GitHub Pages
3. Configure API URLs for production

### Environment Variables for Production
```env
NODE_ENV=production
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/school_document_system
JWT_SECRET=strong_production_secret
FRONTEND_URL=https://yourdomain.com
```

## 🔍 Testing

### Backend Testing
```bash
cd backend
npm test
```

### Frontend Testing
```bash
cd frontend
npm test
```

### Manual Testing Checklist
- [ ] User registration and login
- [ ] Role-based access control
- [ ] File upload functionality
- [ ] Application submission workflow
- [ ] Principal review process
- [ ] Admin user management
- [ ] Email notifications
- [ ] Mobile responsiveness

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## 📞 Support

For technical support or questions:
- Email: admin@pakistanischoolsharjah.com
- Phone: +971-6-xxx-xxxx
- GitHub Issues: Create an issue in this repository

## 🎯 Future Enhancements

- [ ] Mobile application (React Native)
- [ ] Advanced reporting and analytics
- [ ] Integration with school management system
- [ ] Multi-language support (Arabic/English)
- [ ] Digital signature support
- [ ] Automated backup system
- [ ] Advanced file processing (OCR, PDF generation)
- [ ] API for third-party integrations

## 📋 Changelog

### Version 1.0.0 (Current)
- Initial release with core features
- User authentication and authorization
- Document request and approval workflow
- Admin panel for user management
- Responsive UI with dark/light themes

---

**Pakistan Islamia Higher Secondary School Sharjah**  
Document Request & Approval System  
Version 1.0.0 - 2024