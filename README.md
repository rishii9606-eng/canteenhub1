# 🍽️ CanteenHub - Modern Canteen Management System

A comprehensive, cross-platform canteen management system built with Flask, featuring Progressive Web App (PWA) capabilities and desktop applications.

## ✨ Features

- 🌐 **Cross-Platform**: Available as web app, PWA, and desktop application
- 📱 **Mobile-First Design**: Responsive Bootstrap UI that works on all devices
- 🔄 **Automatic Updates**: Built-in update system for both web and desktop versions
- 📴 **Offline Support**: PWA works offline with service worker caching
- 🖥️ **Desktop Apps**: Native desktop applications for Windows, macOS, and Linux
- 👥 **Multi-Role System**: Faculty, Admin, and Canteen staff roles
- 📊 **Order Management**: Complete order lifecycle from placement to completion
- 📋 **Excel Export**: Export orders to Excel for reporting
- 🔔 **Notifications**: Real-time notifications and updates
- 🐳 **Docker Ready**: Easy deployment with Docker and Docker Compose

## 🚀 Quick Start

### Option 1: Download Desktop App (Recommended)

1. Go to the [Releases](releases) section
2. Download the appropriate installer for your platform:
   - Windows: `CanteenHub-Setup-1.0.0.exe`
   - macOS: `CanteenHub-1.0.0.dmg`
   - Linux: `CanteenHub-1.0.0.AppImage`
3. Run the installer and launch CanteenHub

### Option 2: Install as Web App/PWA

1. Download the web package: `CanteenHub-PWA-v1.0.0.zip`
2. Extract and run:
   ```bash
   pip install -r requirements.txt
   python app.py
   ```
3. Open http://localhost:5000 in your browser
4. Click "Install" when prompted to install as PWA

### Option 3: Docker Deployment

```bash
# Clone or download the project
docker-compose up -d
```

## 📋 Requirements

### For Web/PWA Installation:
- Python 3.8 or higher
- pip package manager

### For Desktop App Development:
- Node.js 16+ and npm
- Python 3.8+ (for Flask backend)

### For Docker Deployment:
- Docker and Docker Compose

## 🛠️ Installation Methods

### Method 1: Automatic Installation (Windows)

```powershell
# Download and run the PowerShell build script
.\build.ps1
```

### Method 2: Manual Installation

1. **Install Python Dependencies:**
   ```bash
   pip install Flask>=2.3.3 openpyxl>=3.1.2
   ```

2. **Run the Application:**
   ```bash
   python app.py
   ```

3. **Access the Application:**
   - Open your browser to http://localhost:5000
   - For PWA installation, look for the install prompt

### Method 3: Development Setup

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/canteenhub.git
   cd canteenhub
   ```

2. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   cd electron && npm install
   ```

3. **Run in Development Mode:**
   ```bash
   # Web version
   python app.py
   
   # Desktop version
   cd electron && npm run electron-dev
   ```

## 🏗️ Building from Source

### Build All Platforms:
```bash
python build.py
```

### Build Specific Platform:
```bash
python build.py --platform windows
python build.py --platform macos  
python build.py --platform linux
```

### Build Web/PWA Only:
```bash
python build.py --skip-electron
```

## 🐳 Docker Deployment

### Quick Start with Docker Compose:
```bash
docker-compose up -d
```

### Manual Docker Build:
```bash
docker build -t canteenhub .
docker run -p 5000:5000 -v $(pwd)/data:/app/data canteenhub
```

### Production Deployment:
```bash
# Copy and modify environment variables
cp .env.example .env
nano .env

# Start with production config
docker-compose -f docker-compose.prod.yml up -d
```

## 📱 Platform-Specific Installation

### Windows
- **Desktop**: Download `.exe` installer from releases
- **Web**: Run `install-windows.bat` or `.\build.ps1`
- **Requirements**: Windows 10/11, Python 3.8+

### macOS
- **Desktop**: Download `.dmg` file from releases
- **Web**: Run the Unix installation script
- **Requirements**: macOS 10.15+, Python 3.8+

### Linux
- **Desktop**: Download `.AppImage` or `.deb` package
- **Web**: Run installation script with `bash install-unix.sh`
- **Requirements**: Ubuntu 18.04+/equivalent, Python 3.8+

### Mobile (PWA)
1. Open the web app in your mobile browser
2. Add to Home Screen when prompted
3. Launch from home screen for app-like experience

## 👥 Default Login Credentials

| Role | Username | Password |
|------|----------|----------|
| Faculty | faculty | faculty123 |
| Admin | admin | admin123 |
| Canteen | canteen | canteen123 |

⚠️ **Change these default passwords immediately after first login!**

## 🔧 Configuration

### Environment Variables:
```bash
FLASK_SECRET=your-secret-key-here
FLASK_HOST=127.0.0.1
FLASK_PORT=5000
FLASK_ENV=production
```

### Data Storage:
- Orders: `data/orders.json`
- Users: `data/users.json`
- Notices: `data/factuality.json`

## 🔄 Auto-Updates

### PWA Updates:
- Automatic background updates
- User notification when new version available
- Service worker handles update process

### Desktop App Updates:
- Electron auto-updater integration
- Automatic download and installation
- User prompted before applying updates

### Update Server Setup:
```bash
# Set up update server URL in electron/package.json
"publish": {
  "provider": "generic",
  "url": "https://your-update-server.com/releases"
}
```

## 🔒 Security Features

- Session-based authentication
- Role-based access control
- CSRF protection
- Secure cookie settings
- Input validation and sanitization

## 📊 Usage Guide

### Faculty Users:
1. Login with faculty credentials
2. Place orders for department events
3. View order status and history
4. Change password in profile settings

### Admin Users:
1. Review and approve/reject orders
2. Manage user accounts and departments
3. Export order data to Excel
4. Post notices and announcements
5. View comprehensive dashboard

### Canteen Staff:
1. View approved orders
2. Mark orders as completed
3. Track order fulfillment
4. Access order details and requirements

## 🛠️ Troubleshooting

### Common Issues:

**Port 5000 already in use:**
```bash
# Change port in app.py or set environment variable
export FLASK_PORT=5001
python app.py
```

**PWA not installing:**
- Ensure HTTPS connection (for production)
- Check browser PWA support
- Verify manifest.json is accessible

**Desktop app won't start:**
- Check Python installation
- Verify all dependencies installed
- Run from command line to see error messages

**Docker issues:**
```bash
# Reset Docker containers
docker-compose down -v
docker-compose up --build
```

### Getting Help:
1. Check the [Issues](issues) section
2. Review logs in `logs/` directory
3. Verify system requirements
4. Contact support at support@stfranciscollege.edu

## 🤝 Contributing

1. Fork the repository
2. Create feature branch: `git checkout -b feature/new-feature`
3. Commit changes: `git commit -am 'Add new feature'`
4. Push to branch: `git push origin feature/new-feature`
5. Submit Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Support

- 📧 Email: support@stfranciscollege.edu
- 📞 Phone: +1-XXX-XXX-XXXX
- 🌐 Website: https://stfranciscollege.edu
- 📚 Documentation: https://docs.canteenhub.app

## 🔮 Roadmap

- [ ] Database integration (PostgreSQL/MySQL)
- [ ] Advanced reporting and analytics
- [ ] Mobile app (React Native)
- [ ] API for third-party integrations
- [ ] Inventory management
- [ ] Payment processing
- [ ] Multi-language support
- [ ] Advanced notification system

---

Made with ❤️ for St. Francis College by the CanteenHub Team
