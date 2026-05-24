# AssetVerse Server

## Project Overview
**AssetVerse** is a B2B HR & Asset Management System backend built with **Node.js**, **Express**, and **MongoDB**.  
It provides RESTful APIs for managing companies, employees, assets, requests, assigned assets, and subscription packages.  
The server handles authentication, role-based access, payment integration (Stripe), and analytics.


## Features
- **User Authentication**: Email/password login & optional Google login  
- **Role-Based Access Control**: HR and Employee permissions  
- **Employee Affiliation**: Auto-affiliation when HR approves first asset request  
- **Asset Management**: Add, assign, approve, reject, and return assets  
- **Request Workflow**: Employees can request assets, HR approves/rejects  
- **Package Management**: Stripe integration for upgrading employee limits  
- **Analytics**: Charts for top requested assets & returnable vs non-returnable items  
- **Pagination**: Server-side pagination for asset and employee lists  
- **Optional Features**: PDF generation, notice board, advanced return tracking  

---

## Tech Stack
- Node.js  
- Express.js  
- MongoDB & Mongoose  
- JWT for authentication  
- Stripe for payments  
- Dotenv for environment variables  
- CORS & Helmet for security  

---

## API Endpoints Overview
### Auth
- `POST /api/auth/register` → HR or Employee registration  
- `POST /api/auth/login` → Login and JWT token generation  

### Users
- `GET /api/users/me` → Get current user profile  
- `PUT /api/users/me` → Update profile (limited fields)  

### Assets
- `POST /api/assets` → Add new asset (HR only)  
- `GET /api/assets` → List all assets  
- `PUT /api/assets/:id` → Update asset details  
- `DELETE /api/assets/:id` → Delete asset  

### Requests
- `POST /api/requests` → Employee requests an asset  
- `GET /api/requests` → HR view all requests  
- `PUT /api/requests/:id/approve` → Approve asset request (creates affiliation)  
- `PUT /api/requests/:id/reject` → Reject request  

### Assigned Assets
- `GET /api/assigned` → Employee view assigned assets  
- `PUT /api/assigned/:id/return` → Return asset (optional)  

### Packages & Payments
- `GET /api/packages` → List available subscription packages  
- `POST /api/payments` → Stripe payment for package upgrade  

---

## Database Collections
- **users**: HR & Employee data  
- **employeeAffiliations**: Tracks employee-company relationships  
- **assets**: All company assets  
- **requests**: Asset requests  
- **assignedAssets**: Assigned/returned assets  
- **packages**: Subscription package info  
- **payments**: Stripe payment records 
