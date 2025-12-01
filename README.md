# FilStart

A modern, feature-rich Laravel application with Filament admin panel for content management and business website solutions.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [System Requirements](#system-requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [Project Structure](#project-structure)
- [Database](#database)
- [Development](#development)
- [Testing](#testing)
- [Deployment](#deployment)
- [API Documentation](#api-documentation)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

FilStart is a comprehensive Laravel-based web application that provides a powerful content management system with Filament admin panel. It's designed for businesses and organizations that need a robust platform to manage their online presence, including pages, blogs, products, services, galleries, and more.

The application follows modern software architecture principles with a service layer pattern, observers, custom notifications, and extensive customization options through Filament's powerful admin interface.

## ✨ Features

### Content Management
- **Dynamic Pages**: Create and manage unlimited pages with categories
- **Blog System**: Full-featured blog with categories and rich content editor
- **Product Catalog**: Product management with categories and specifications
- **Services Management**: Showcase your services with detailed descriptions
- **Gallery**: Image gallery management with media library integration
- **Team Members**: Display your team with profiles and roles
- **References**: Client references and testimonials
- **FAQ System**: Frequently asked questions management

### Admin Panel (Filament)
- **Modern UI**: Clean and intuitive admin interface powered by Filament 3.3
- **Media Manager**: Advanced media management with Spatie Media Library
- **Settings Management**: Dynamic site settings with Spatie Laravel Settings
- **Multi-language Support**: Language switching capabilities
- **Profile Management**: User profile editing functionality
- **Custom Avatar Provider**: Personalized avatar handling
- **Tags System**: Content tagging for better organization
- **Analytics Integration**: Google Analytics integration via Spatie

### Technical Features
- **SEO Optimized**: Built-in sitemap generation
- **Redirect Management**: Handle URL redirects efficiently
- **Contact Forms**: Handle and manage contact messages
- **Notifications System**: Custom notification handlers
- **Model Observers**: Automated model event handling
- **Service Layer**: Clean architecture with service classes
- **API Support**: RESTful API endpoints
- **Security**: Laravel's built-in security features

## 🛠 Technology Stack

### Backend
- **PHP**: ^8.2
- **Laravel Framework**: ^12.0
- **Filament**: ^3.3 (Admin Panel)
- **Database**: MySQL/PostgreSQL/SQLite

### Frontend
- **Vite**: ^7.0.4 (Build Tool)
- **Tailwind CSS**: ^4.0.0
- **Alpine.js** (via Filament/Livewire)
- **Axios**: ^1.11.0

### Key Packages
- **Filament Packages**:
  - `filament/filament` - Core admin panel
  - `filament/spatie-laravel-media-library-plugin` - Media management
  - `filament/spatie-laravel-settings-plugin` - Settings management
  - `filament/spatie-laravel-tags-plugin` - Tagging system
  - `bezhansalleh/filament-language-switch` - Language switching
  - `joaopaulolndev/filament-edit-profile` - Profile editing
  - `tomatophp/filament-media-manager` - Enhanced media manager

- **Spatie Packages**:
  - `spatie/laravel-analytics` - Google Analytics integration
  - `spatie/laravel-settings` - Application settings
  - `spatie/laravel-sitemap` - XML sitemap generation

### Development Tools
- **Testing**: Pest PHP ^3.8
- **Code Quality**: Laravel Pint ^1.13
- **Development Environment**: Laravel Sail ^1.41
- **Debugging**: Laravel Pail ^1.2.2

## 📦 System Requirements

- **PHP**: 8.2 or higher
- **Composer**: Latest version
- **Node.js**: 18.x or higher
- **NPM/Yarn**: Latest version
- **Database**: MySQL 8.0+, PostgreSQL 13+, or SQLite 3.35+
- **Web Server**: Apache 2.4+ or Nginx 1.18+
- **PHP Extensions**:
  - BCMath
  - Ctype
  - Fileinfo
  - JSON
  - Mbstring
  - OpenSSL
  - PDO
  - Tokenizer
  - XML
  - GD or Imagick (for image processing)

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/yusuferdemyamali/FilStart.git
cd FilStart
```

### 2. Install PHP Dependencies

```bash
composer install
```

### 3. Install Node.js Dependencies

```bash
npm install
```

### 4. Environment Configuration

```bash
# Copy the environment file
cp .env.example .env

# Generate application key
php artisan key:generate
```

### 5. Configure Database

Edit your `.env` file with your database credentials:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=filstart
DB_USERNAME=your_username
DB_PASSWORD=your_password
```

### 6. Run Migrations

```bash
# Run migrations
php artisan migrate

# (Optional) Seed the database with sample data
php artisan db:seed
```

### 7. Create Storage Link

```bash
php artisan storage:link
```

### 8. Build Frontend Assets

```bash
# Development
npm run dev

# Production
npm run build
```

### 9. Create Admin User

```bash
php artisan make:filament-user
```

Follow the prompts to create your admin account.

### 10. Start Development Server

```bash
php artisan serve
```

Visit `http://localhost:8000` for the frontend and `http://localhost:8000/admin` for the admin panel.

## ⚙️ Configuration

### Environment Variables

Key environment variables to configure:

```env
# Application
APP_NAME=FilStart
APP_ENV=local
APP_DEBUG=true
APP_URL=http://localhost

# Database
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=filstart

# Mail Configuration
MAIL_MAILER=smtp
MAIL_HOST=mailpit
MAIL_PORT=1025

# Google Analytics (Optional)
ANALYTICS_VIEW_ID=
```

### Site Settings

Configure site-wide settings through the Filament admin panel:
- Navigate to Admin Panel → Settings
- Configure company information, contact details, social media links, etc.

### Media Configuration

The application uses Spatie Media Library for file uploads. Configure storage in:
- `config/filesystems.php` - Storage disks
- `config/filament-media-manager.php` - Media manager settings

### Analytics Setup

To enable Google Analytics:
1. Set up Google Analytics and obtain API credentials
2. Configure credentials in `config/analytics.php`
3. Set `ANALYTICS_VIEW_ID` in `.env`

## 📁 Project Structure

```
filstart/
├── app/
│   ├── Console/           # Artisan commands
│   ├── Filament/          # Filament admin customizations
│   │   ├── Pages/         # Custom admin pages
│   │   ├── Resources/     # Model resources
│   │   └── Widgets/       # Dashboard widgets
│   ├── Http/
│   │   ├── Controllers/   # HTTP controllers
│   │   └── Middleware/    # Custom middleware
│   ├── Models/            # Eloquent models
│   │   ├── About.php
│   │   ├── Blog.php
│   │   ├── Product.php
│   │   ├── Service.php
│   │   └── ...
│   ├── Notifications/     # Custom notifications
│   ├── Observers/         # Model observers
│   ├── Providers/         # Service providers
│   ├── Services/          # Business logic layer
│   └── Settings/          # Settings classes
├── config/                # Configuration files
├── database/
│   ├── migrations/        # Database migrations
│   ├── seeders/          # Database seeders
│   └── factories/        # Model factories
├── public/               # Public assets
├── resources/
│   ├── css/              # Stylesheets
│   ├── js/               # JavaScript files
│   └── views/            # Blade templates
├── routes/
│   ├── web.php           # Web routes
│   ├── api.php           # API routes
│   └── console.php       # Console commands
├── storage/              # Application storage
└── tests/                # Test files
    ├── Feature/          # Feature tests
    └── Unit/             # Unit tests
```

## 💾 Database

### Main Models

- **About**: Company about information
- **Blog**: Blog posts with rich content
- **BlogCategory**: Blog categorization
- **Product**: Product catalog items
- **ProductCategory**: Product categorization
- **Service**: Service offerings
- **ServiceCategory**: Service categorization
- **Page**: Dynamic pages
- **PageCategory**: Page categorization
- **Gallery**: Image galleries
- **Team**: Team member profiles
- **Reference**: Client references
- **Faq**: FAQ entries
- **ContactMessage**: Contact form submissions
- **Redirect**: URL redirect management
- **SiteSetting**: Site-wide settings
- **CompanySetting**: Company information

### Relationships

Models are interconnected with Laravel's Eloquent relationships:
- Categories have many items (Products, Blogs, Services, Pages)
- Items belong to categories
- Media library integration for file attachments
- Tagging system for flexible categorization

## 🔧 Development

### Running Development Server

```bash
# Start Laravel development server
php artisan serve

# Start Vite development server (in another terminal)
npm run dev
```

### Code Quality

```bash
# Format code with Laravel Pint
./vendor/bin/pint

# Run static analysis
./vendor/bin/phpstan analyse
```

### Clear Caches

```bash
# Clear all caches
php artisan optimize:clear

# Or individually:
php artisan cache:clear
php artisan config:clear
php artisan route:clear
php artisan view:clear
```

### Generate Sitemap

```bash
php artisan sitemap:generate
```

## 🧪 Testing

The project uses Pest PHP for testing.

### Run All Tests

```bash
# Run all tests
php artisan test

# Or using Pest directly
./vendor/bin/pest

# Run with coverage
./vendor/bin/pest --coverage
```

### Run Specific Tests

```bash
# Feature tests only
./vendor/bin/pest tests/Feature

# Unit tests only
./vendor/bin/pest tests/Unit

# Specific test file
./vendor/bin/pest tests/Feature/ExampleTest.php
```

### Writing Tests

Tests are located in the `tests/` directory:
- `tests/Feature/` - Integration/feature tests
- `tests/Unit/` - Unit tests

Example test:

```php
test('homepage loads successfully', function () {
    $response = $this->get('/');
    $response->assertStatus(200);
});
```

## 🚢 Deployment

### Production Checklist

1. **Environment Configuration**
```bash
APP_ENV=production
APP_DEBUG=false
```

2. **Optimize Application**
```bash
composer install --optimize-autoloader --no-dev
php artisan config:cache
php artisan route:cache
php artisan view:cache
npm run build
```

3. **Set Permissions**
```bash
chmod -R 755 storage bootstrap/cache
```

4. **Database Migration**
```bash
php artisan migrate --force
```

5. **Queue Workers** (if using queues)
```bash
php artisan queue:work --daemon
```

### Web Server Configuration

#### Nginx Example

```nginx
server {
    listen 80;
    server_name your-domain.com;
    root /path/to/filstart/public;

    add_header X-Frame-Options "SAMEORIGIN";
    add_header X-Content-Type-Options "nosniff";

    index index.php;

    charset utf-8;

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    location = /favicon.ico { access_log off; log_not_found off; }
    location = /robots.txt  { access_log off; log_not_found off; }

    error_page 404 /index.php;

    location ~ \.php$ {
        fastcgi_pass unix:/var/run/php/php8.2-fpm.sock;
        fastcgi_param SCRIPT_FILENAME $realpath_root$fastcgi_script_name;
        include fastcgi_params;
    }

    location ~ /\.(?!well-known).* {
        deny all;
    }
}
```

### Using Laravel Sail (Docker)

```bash
# Start containers
./vendor/bin/sail up -d

# Run migrations
./vendor/bin/sail artisan migrate

# Access shell
./vendor/bin/sail shell
```

## 📚 API Documentation

API endpoints are available under the `/api` prefix. 

### Authentication

The API uses Laravel Sanctum for authentication. Include the token in the Authorization header:

```
Authorization: Bearer {your-token}
```

### Example Endpoints

```
GET  /api/blogs          # List all blogs
GET  /api/blogs/{id}     # Get specific blog
GET  /api/products       # List all products
GET  /api/services       # List all services
POST /api/contact        # Submit contact form
```

For detailed API documentation, consider implementing tools like:
- Laravel API Documentation Generator
- Swagger/OpenAPI
- Postman Collections

## 🤝 Contributing

We welcome contributions! Please follow these guidelines:

1. **Fork the Repository**
2. **Create a Feature Branch**
```bash
git checkout -b feature/amazing-feature
```

3. **Commit Your Changes**
```bash
git commit -m 'Add some amazing feature'
```

4. **Push to the Branch**
```bash
git push origin feature/amazing-feature
```

5. **Open a Pull Request**

### Coding Standards

- Follow PSR-12 coding standards
- Write tests for new features
- Update documentation as needed
- Use Laravel Pint for code formatting

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👨‍💻 Author

**Yusuf Erdem Yamalı**
- GitHub: [@yusuferdemyamali](https://github.com/yusuferdemyamali)

## 🙏 Acknowledgments

- [Laravel](https://laravel.com) - The PHP Framework
- [Filament](https://filamentphp.com) - Admin Panel
- [Spatie](https://spatie.be) - Laravel Packages
- [Tailwind CSS](https://tailwindcss.com) - CSS Framework

## 📞 Support

For support, please:
- Open an issue in the GitHub repository
- Check existing documentation
- Review closed issues for solutions

## 🔄 Changelog

### Version 1.0.0 (Current)
- Initial release
- Complete content management system
- Filament admin panel integration
- Multi-language support
- Media library integration
- SEO optimization features

---

Made with ❤️ using Laravel and Filament
