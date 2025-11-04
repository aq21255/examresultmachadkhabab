# Exam Results Portal 2025
## Khabbab Bin Aratti Institute for Islamic Studies & Cultural

### Setup Instructions

1. **Install Dependencies:**
```bash
npm install
```

2. **Add Logo:**
   - Place your logo image at: `public/assets/logo.jpg`
   - The logo will appear in the header of all pages

3. **Start Server:**
```bash
npm start
```

For development with auto-reload:
```bash
npm run dev
```

4. **Access the Website:**
   - Main page: http://localhost:5000
   - Admin login: Click "Admin Login" link
   - Default admin credentials:
     - Username: `admin`
     - Password: `admin123`

### Features

✅ Modern Islamic-themed design (light green + white gradient)
✅ Responsive layout (mobile, tablet, desktop)
✅ QR code scanning for mobile devices
✅ PDF download functionality
✅ Print result functionality
✅ Student photo upload
✅ CSV export for admin
✅ Auto-generate exam numbers
✅ Dynamic subject entry
✅ Real-time grade calculation

### File Structure

```
├── server.js              # Express backend server
├── package.json           # Node.js dependencies
├── students.db            # SQLite database (auto-created)
├── public/
│   ├── index.html         # React frontend
│   └── assets/
│       └── logo.jpg       # Institute logo
└── uploads/
    └── photos/            # Uploaded student photos
```

### Technology Stack

- **Backend:** Node.js + Express + SQLite
- **Frontend:** React + TailwindCSS
- **QR Codes:** qrcode npm package
- **PDF Generation:** jsPDF
- **File Uploads:** Multer
- **QR Scanning:** html5-qrcode

