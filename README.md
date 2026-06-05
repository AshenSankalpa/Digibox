<div align="center">

# 🌟 DigiBox

### Digital Community Fundraising Platform with Trust and Transparency

[![Live Demo](https://img.shields.io/badge/🔴_Live_Demo-digibox.kalvexit.com-FF0000?style=for-the-badge)](https://digibox.kalvexit.com)
[![Version](https://img.shields.io/badge/version-1.0.0-blue?style=for-the-badge)]()
[![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)]()

*A comprehensive digital fundraising platform connecting cause creators with donors through a secure, transparent, and efficient three-tier approval workflow.*

</div>

---

## 🚀 Live Demo & Access

Experience the platform live at: **[https://digibox.kalvexit.com](https://digibox.kalvexit.com)**

### 🔐 Demo Credentials

Use the following credentials to access the admin dashboard and explore the platform's capabilities:

| Role | Email | Password |
| :--- | :--- | :--- |
| **Admin** | `admin@example.com` | `Admin@123` |

> **Note:** The platform includes multiple roles (GS Officer, DS Officer, Creator, Donor) which can be managed via the Admin dashboard.

---

## 📖 Overview

DigiBox is built with modern web technologies to ensure proper verification, documentation, and tracking of every fundraising initiative from submission to completion.

---

## ✨ Key Features

### 🎯 Multi-Role System
- **5 User Roles**: Admin, GS Officer, DS Officer, Cause Creator, Donor
- **Role-Based Access Control**: Customized dashboards and permissions for each role
- **Secure Authentication**: JWT-based token authentication with bcrypt password hashing

### 📋 Cause Management
- **Complete Cause Creation**: Title, description, category, target amount, beneficiary details
- **NIC Validation**: Sri Lankan NIC number verification (12 digits or 9 digits + V/X)
- **Document Upload**: PDF evidence files (max 2MB) with NIC photos, bank statements, and supporting documents
- **Real-Time Status Tracking**: Monitor approval progress through all stages

### ✅ Three-Tier Approval Workflow
1. **Admin Approval**: Initial verification and assignment to appropriate officers
2. **GS Officer Verification**: Ground-level verification with professional approval certificates
3. **DS Final Approval**: Final authorization with official documentation

### 📄 Professional Documentation
- **Branded PDF Certificates**: Professional letterhead design with DigiBox branding
- **Official Seals**: Color-coded official stamps for GS (Purple) and DS (Indigo)
- **Structured Layout**: Organized sections with cause details, verification notes, and signatures
- **Auto-Generated Reference Numbers**: Unique tracking numbers for each approval

### 💰 Fund Tracking
- **Live Progress Monitoring**: Visual progress bars showing funding status
- **Donor Count**: Track number of contributors for each cause
- **Target Achievement**: Status indicators (Not Started, Ongoing, Target Achieved)
- **Formatted Currency Display**: Consistent thousand-separator formatting (LKR 5,000)

### 📊 Analytics Dashboard
- **Statistical Overview**: Total causes, approved, pending, rejected counts
- **Monthly Analytics**: Visual charts showing cause creation trends
- **Fund Raised Tracking**: Total funds collected across all approved causes
- **Active Causes Monitor**: Real-time donation progress for approved causes

### 🗺️ Geographic Hierarchy
- **Cascading Selection**: District → Division → GS Area dropdown system
- **Automatic Officer Assignment**: GS and DS officers mapped by geographic codes
- **Location-Based Management**: Officers see only causes in their jurisdiction

### 👤 Profile Management
- **Unified Profile System**: Single profile page for all roles with sidebar navigation
- **Profile Picture Upload**: Image upload with 5MB limit
- **Password Reset**: Secure password change functionality
- **Administrative Details**: District, division, and area information for officers

---

## 🛠️ Technology Stack

### Frontend
- **Framework**: React 18.2.0
- **Styling**: Tailwind CSS 3.4.18
- **Routing**: React Router DOM 6.8.0
- **HTTP Client**: Axios 1.12.2
- **Charts**: Recharts 3.3.0, Chart.js 4.5.1
- **Icons**: React Icons 5.5.0
- **PDF Generation**: jsPDF 4.0.0
- **UI Components**: Material-UI 7.3.4, Lucide React

### Backend
- **Runtime**: Node.js with Express 5.1.0
- **Database**: MongoDB with Mongoose 8.19.2
- **Authentication**: JWT 9.0.2, bcryptjs 3.0.2
- **File Upload**: Multer 2.0.2
- **Email**: Nodemailer 7.0.12
- **PDF Generation**: PDFKit 0.17.2
- **Development**: Nodemon 3.1.10

### Security
- **JWT Tokens**: Secure authentication with Bearer tokens
- **Password Hashing**: bcrypt with 10 salt rounds
- **Role Authorization**: Middleware-based access control
- **Input Validation**: Server-side validation for all inputs
- **File Validation**: Type and size restrictions on uploads

---

## 📁 Project Structure

```
DigiBox/
├── backend/
│   ├── config/
│   │   └── db.js                 # MongoDB connection
│   ├── controllers/
│   │   └── adminController.js    # Admin business logic
│   ├── middleware/
│   │   └── authMiddleware.js     # JWT & role authorization
│   ├── models/
│   │   ├── causeModel.js         # Cause schema with indexes
│   │   ├── userModel.js          # User schema
│   │   ├── DistrictModel.js      # Geographic hierarchy models
│   │   ├── DivisionModel.js
│   │   └── GSAreaModel.js
│   ├── routes/
│   │   ├── adminRoutes.js        # Admin endpoints
│   │   ├── authRoutes.js         # Login/register
│   │   ├── causeRoutes.js        # Cause CRUD & stats
│   │   ├── dashboardRoutes.js    # Dashboard data
│   │   ├── donorRoutes.js        # Donor operations
│   │   ├── dsRoutes.js           # DS officer endpoints
│   │   ├── gsRoutes.js           # GS officer endpoints
│   │   └── profileRoutes.js      # User profile management
│   ├── uploads/                  # File storage directory
│   ├── utils/
│   │   └── email.js              # Email service
│   ├── .env                      # Environment variables
│   ├── index.js                  # Server entry point
│   └── package.json
│
├── frontend/
│   ├── public/
│   │   ├── index.html
│   │   └── assets/
│   │       └── images/
│   ├── src/
│   │   ├── components/
│   │   │   ├── dashboard/
│   │   │   │   ├── Sidebar.jsx            # Role-based navigation
│   │   │   │   ├── StatCard.jsx           # Dashboard statistics
│   │   │   │   ├── BarChartView.jsx       # Analytics charts
│   │   │   │   ├── PieChartView.jsx
│   │   │   │   ├── ProgressBar.jsx
│   │   │   │   └── UserProfileMenu.jsx
│   │   │   ├── Navbar.jsx
│   │   │   ├── Footer.jsx
│   │   │   └── FormInput.jsx
│   │   ├── pages/
│   │   │   ├── LandingPage.jsx
│   │   │   ├── Login.jsx
│   │   │   ├── Signup.jsx
│   │   │   ├── Profile.jsx              # Unified profile with sidebar
│   │   │   ├── admin/
│   │   │   │   ├── AdminDashboard.jsx
│   │   │   │   ├── ApproveCauses.jsx
│   │   │   │   ├── PublishCauses.jsx
│   │   │   │   ├── ManageUsers.jsx
│   │   │   │   └── AddOfficer.jsx
│   │   │   ├── creator/
│   │   │   │   ├── CreatorDashboard.jsx  # Optimized with indexes
│   │   │   │   ├── CreateCause.jsx       # Enhanced with NIC & evidence
│   │   │   │   └── MyCauses.jsx
│   │   │   ├── donor/
│   │   │   │   ├── DonorDashboard.jsx
│   │   │   │   ├── BrowseCauses.jsx
│   │   │   │   ├── CauseDetails.jsx
│   │   │   │   ├── Donate.jsx
│   │   │   │   └── DonationHistory.jsx
│   │   │   ├── gs/
│   │   │   │   ├── GSDashboard.jsx
│   │   │   │   ├── PendingCauses.jsx     # Professional PDF generation
│   │   │   │   └── Documents.jsx
│   │   │   └── ds/
│   │   │       ├── DSDashboard.jsx
│   │   │       ├── DSPendingCauses.jsx   # Professional PDF generation
│   │   │       └── DSDocuments.jsx
│   │   ├── services/
│   │   │   ├── donorService.js
│   │   │   ├── dsService.js
│   │   │   └── gsService.js
│   │   ├── styles/
│   │   │   ├── global.css
│   │   │   └── landing.css
│   │   ├── App.js                        # Main routing
│   │   ├── App.css
│   │   └── index.js
│   ├── tailwind.config.js               # Custom purple/indigo theme
│   ├── package.json
│   └── README.md
│
└── README.md                            # This file
```

---

## 🚀 Getting Started

### Prerequisites
- **Node.js**: v14.x or higher
- **MongoDB**: v4.x or higher (local or MongoDB Atlas)
- **npm**: v6.x or higher

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/DigiBox.git
cd DigiBox
```

2. **Backend Setup**
```bash
cd backend
npm install
```

Create `.env` file in backend directory:
```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/digibox
JWT_SECRET=your_super_secret_jwt_key_here_change_in_production
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-email-app-password
```

3. **Frontend Setup**
```bash
cd ../frontend
npm install
```

4. **Start the Application**

**Terminal 1 - Backend:**
```bash
cd backend
npm start
```
Backend will run on `http://localhost:5000`

**Terminal 2 - Frontend:**
```bash
cd frontend
npm start
```
Frontend will run on `http://localhost:3000`

---

## 👥 Default Admin Account

On first startup, a default admin account is automatically created:

```
Email: admin@example.com
Password: Admin@123
```

⚠️ **Important**: Change the admin password immediately after first login in production environments!

---

## 📱 User Roles & Capabilities

### 🔧 Administrator
- Approve/reject causes submitted by creators
- Manage user accounts (create, update, delete)
- Add GS and DS officers with geographic assignments
- Publish approved causes for donor visibility
- View system-wide analytics and reports
- Access admin structure hierarchy

### 📝 Cause Creator
- Submit new fundraising causes with complete details
- Upload evidence documents (NIC, bank statements, supporting docs)
- Track cause status through approval workflow
- Monitor active causes with live donation progress
- View monthly analytics of submitted causes
- Receive notifications on approval/rejection

### 🏛️ Grama Seva (GS) Officer
- Review causes assigned to their geographic area
- Verify beneficiary information and evidence
- Approve/reject causes with verification notes
- Generate professional approval certificates with signature
- View all causes in their jurisdiction
- Access pending causes dashboard

### 🏢 Divisional Secretary (DS)
- Final approval authority for GS-approved causes
- Review division-level causes
- Generate official final approval certificates
- Access GS approval documents
- Monitor division-wide cause statistics
- Authorize cause publication

### 💝 Donor
- Browse published and approved causes
- View detailed cause information with beneficiary details
- Make donations to active causes
- Track donation history
- View completed causes
- Filter causes by category and status

---

## 🔐 Authentication & Security

### JWT Token Flow
1. User logs in with email/password
2. Server validates credentials and generates JWT token
3. Token stored in `localStorage` on client
4. Token sent in `Authorization: Bearer <token>` header for protected routes
5. Backend middleware verifies token and extracts user info
6. Role-based access control checks user permissions

### Password Security
- **Hashing**: bcrypt with 10 salt rounds
- **Validation**: Minimum 6 characters required
- **Reset**: Requires current password verification

### File Upload Security
- **Type Validation**: Only PDF files accepted for evidence
- **Size Limit**: 2MB maximum (configurable)
- **Server Validation**: Backend double-checks file type and size

---

## 📊 Database Schema

### User Schema
```javascript
{
  username: String,
  email: String (unique),
  password: String (hashed),
  role: Enum ["admin", "gs", "ds", "creator", "donor"],
  profileImage: String,
  districtCode: String,
  districtName: String,
  divisionCode: String,
  divisionName: String,
  areaCode: String,
  areaName: String,
  createdAt: Date,
  updatedAt: Date
}
```

### Cause Schema
```javascript
{
  creator: ObjectId (ref User),
  title: String,
  description: String,
  category: Enum,
  requiredAmount: Number,
  
  // Beneficiary Info
  beneficiaryName: String,
  beneficiaryContact: String,
  beneficiaryAddress: String,
  beneficiaryNIC: String,
  beneficiaryAccountName: String,
  beneficiaryBank: String,
  beneficiaryAccountNumber: String,
  beneficiaryBranch: String,
  
  // Evidence & Documents
  evidenceFile: String,
  evidenceFileType: String,
  gsDocument: String,
  dsDocument: String,
  
  // Geographic Assignment
  districtCode: String,
  districtName: String,
  divisionCode: String,
  divisionName: String,
  areaCode: String,
  areaName: String,
  
  // Officer Assignment
  gsOfficer: ObjectId (ref User),
  dsOfficer: ObjectId (ref User),
  
  // Approval Status
  adminStatus: Enum ["pending", "approved", "rejected"],
  gsStatus: Enum ["pending", "approved", "rejected"],
  dsStatus: Enum ["pending", "approved", "rejected"],
  finalStatus: Enum ["pending", "approved", "rejected"],
  
  // Verification Details
  gsVerification: {
    remarks: String,
    date: Date,
    signature: String
  },
  dsVerification: {
    approvalNote: String,
    date: Date,
    signature: String
  },
  
  // Fund Tracking
  fundsRaised: Number (default: 0),
  donorsCount: Number (default: 0),
  
  // Publication
  isPublished: Boolean,
  publishedAt: Date,
  publishedBy: ObjectId (ref User),
  
  isCompleted: Boolean,
  createdAt: Date,
  updatedAt: Date
}
```

### Performance Indexes
```javascript
// Optimized for creator dashboard queries
causeSchema.index({ creator: 1, createdAt: -1 });
causeSchema.index({ creator: 1, dsStatus: 1 });
causeSchema.index({ creator: 1, adminStatus: 1, gsStatus: 1, dsStatus: 1 });
```

---

## 🎨 Theme & Design

### Color Palette
- **Primary**: `#8B5CF6` (Purple) - Used for GS branding
- **Secondary**: `#6366F1` (Indigo) - Used for DS branding
- **Background**: `#0f172a` (Dark Navy)
- **Card Background**: `#1e293b` (Dark Gray)
- **Text**: White/Gray variants

### Typography
- **Font Family**: System fonts (Arial, sans-serif)
- **Headings**: Bold, Primary color
- **Body**: Regular weight, White/Gray

---

## 🔧 Configuration

### Backend Configuration (`.env`)
```env
# Server
PORT=5000

# Database
MONGODB_URI=mongodb://localhost:27017/digibox

# JWT
JWT_SECRET=your_secret_key_min_32_characters

# Email (SMTP)
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-app-password

# File Upload
MAX_FILE_SIZE=2097152  # 2MB in bytes
```

### Frontend Configuration
API base URL is set in Axios calls: `http://localhost:5000`

For production, update all API URLs to your deployed backend URL.

---

## 📈 Performance Optimizations

### Backend
1. **Database Indexes**: Added compound indexes for frequent creator queries
2. **Parallel Queries**: Using `Promise.all()` for independent database operations
3. **Lean Queries**: Using `.lean()` for read-only operations to skip Mongoose overhead
4. **Field Selection**: Only fetching required fields with `.select()`
5. **Payload Limit**: Increased to 100MB for PDF document uploads

### Frontend
1. **Code Splitting**: React lazy loading for route-based chunks
2. **Optimized Rendering**: Proper use of React hooks and memoization
3. **Image Optimization**: Compressed images and lazy loading
4. **Bundle Size**: Production build with minification

### Results
- Creator dashboard load time: **Reduced from 30s to <3s**
- API response times: **Average <500ms**
- PDF generation: **Client-side for instant preview**

---

## 📧 Email Notifications

### Automated Emails Sent:
- **Cause Rejection**: Notifies creator when cause is rejected (Admin/GS/DS)
- **GS Approval**: Notifies DS officer when cause is GS-approved
- **DS Approval**: Notifies admin when cause receives final approval
- **Admin Actions**: Various system notifications

### Email Configuration
Uses Nodemailer with SMTP. For Gmail:
1. Enable 2-factor authentication
2. Generate an app-specific password
3. Use app password in `EMAIL_PASS` env variable

---

## 🧪 Testing

### Manual Testing Checklist
- [ ] User registration and login for all roles
- [ ] Cause creation with evidence file upload
- [ ] Admin approval workflow
- [ ] GS verification with PDF generation
- [ ] DS final approval with PDF generation
- [ ] PDF preview matches downloaded document
- [ ] Fund tracking and progress bars
- [ ] Profile management and password reset
- [ ] Geographic hierarchy cascading dropdowns
- [ ] Dashboard analytics and charts

---

## 🚀 Deployment

### Backend Deployment (Heroku/Railway/Render)
1. Set environment variables in hosting platform
2. Update MongoDB URI to production database
3. Configure CORS for production frontend URL
4. Set `NODE_ENV=production`

### Frontend Deployment (Vercel/Netlify)
1. Update API URLs to production backend
2. Build production bundle: `npm run build`
3. Deploy `build` folder
4. Configure environment variables if needed

### Database (MongoDB Atlas)
1. Create cluster on MongoDB Atlas
2. Whitelist deployment server IPs
3. Update `MONGODB_URI` with Atlas connection string

---

## 🐛 Troubleshooting

### Common Issues

**Issue**: Backend PayloadTooLargeError
- **Solution**: Increase body-parser limit in `index.js` (currently 100MB)

**Issue**: Creator dashboard takes too long to load
- **Solution**: Database indexes have been added. Restart backend to build indexes.

**Issue**: PDF preview and downloaded PDF don't match
- **Solution**: Fixed. PDFs now generated on frontend and sent to backend.

**Issue**: CORS errors
- **Solution**: Ensure backend CORS is configured for frontend URL

**Issue**: JWT token invalid
- **Solution**: Check JWT_SECRET matches between .env and frontend localStorage

---

## 📝 API Documentation

### Authentication Endpoints
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user

### Cause Endpoints
- `POST /api/cause/create` - Create new cause (creator)
- `GET /api/cause/my-causes` - Get user's causes (creator)
- `GET /api/cause/stats` - Get creator statistics
- `GET /api/cause/analytics/monthly` - Monthly analytics

### Admin Endpoints
- `GET /api/admin/pending-causes` - Get causes pending admin approval
- `PUT /api/admin/approve/:id` - Approve cause
- `PUT /api/admin/reject/:id` - Reject cause
- `GET /api/admin/gs-hierarchy` - Get geographic hierarchy

### GS Officer Endpoints
- `GET /api/gs/pending-causes` - Get GS pending causes
- `PUT /api/gs/approve/:id` - Approve with PDF
- `PUT /api/gs/reject/:id` - Reject with reason

### DS Officer Endpoints
- `GET /api/ds/pending-causes` - Get DS pending causes
- `PUT /api/ds/approve/:id` - Final approval with PDF
- `PUT /api/ds/reject/:id` - Reject with reason

### Profile Endpoints
- `GET /api/profile` - Get user profile
- `PUT /api/profile` - Update profile
- `PUT /api/profile/upload-image` - Upload profile image
- `PUT /api/profile/reset-password` - Reset password

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 👨‍💻 Authors

- **DigiBox Development Team**

---

## 🙏 Acknowledgments

- React and Node.js communities
- MongoDB documentation
- jsPDF library for PDF generation
- Tailwind CSS for styling framework
- All contributors and testers

---

## 📞 Support

For support, email support@digibox.com or open an issue in the repository.

---

## 🔮 Future Enhancements

- [ ] SMS notifications for approval updates
- [ ] Mobile app (React Native)
- [ ] Payment gateway integration
- [ ] Real-time chat support
- [ ] Advanced analytics with data visualization
- [ ] Multi-language support
- [ ] Blockchain-based donation tracking
- [ ] AI-powered fraud detection
- [ ] Social media integration
- [ ] Automated tax receipt generation

---

**Made with ❤️ by DigiBox Team**

**Powered by: DigiBox - Digital Community Fundraising Platform with Trust and Transparancy**
