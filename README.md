<p align="center">
  <img src="https://img.shields.io/badge/.NET-9.0-512BD4?style=for-the-badge&logo=dotnet&logoColor=white" alt=".NET 9" />
  <img src="https://img.shields.io/badge/ASP.NET_Core-MVC-512BD4?style=for-the-badge&logo=dotnet&logoColor=white" alt="ASP.NET Core MVC" />
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/Azure_Blob_Storage-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" alt="Azure Blob Storage" />
  <img src="https://img.shields.io/badge/Bootstrap-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white" alt="Bootstrap" />
</p>

<img src="./assets/box-logo-login.png" alt="Logo"> BOX2ERP

**BOX2ERP** is a streamlined, role-based ERP and MRP web application built with **ASP.NET Core 9 MVC**. While BOX2ERP does not claim to be a "full-featured" corporate ERP suite yet, it was born with that ambition. It is a continuously evolving system designed to meet the essential ERP and MRP needs of small to medium-sized enterprises (SMEs), focusing on practical utility over unnecessary complexity.
It is designed to streamline the end-to-end order lifecycle—covering everything from sales entry and production planning to procurement, logistics, and shipment tracking.

---

## ✨ Features

### 📊 Dashboard
- Real-time KPI summary cards (orders this year, open orders, shipped, idle)
- Interactive **Chart.js** pie chart — orders per customer
- Weekly planners: planned shipments, overdue orders, recently shipped
- Embedded **Google Calendar** integration for team events

### 🛒 Order & Shipment Planning
- Order lifecycle management with multi-status tracking
- Role-segmented editing: **Sales**, **Production**, and **Logistics** views
- Location-based production tracking (raw material → laser → bending → welding → paint → packing → shipping)
- Target & planned shipment date management with overdue detection
- Shipment type support with sub-categories: **Sea**, **Air**, **Truck**

### 📦 Product Management
- Product catalog with grouping, tagging, and component tracking
- Child and Parent Components Structure
- Visualization of Child and Parent component relationships with BOM list
- Versioning System
- Product categories, paint types, and paint type rules

### 👥 Customer & Supplier Management
- Customer master data
- Supplier directory with active/inactive status filtering
- Dedicated supplier portal pages

### 🚚 Logistics Requests & Shipments
- Request management per order with completion tracking
- Creating shipment cards for requested shipments with shipment details

### 📝 Task Management
- Task creation with assignments and attachments

### 🔐 Authentication & Authorization
- **ASP.NET Core Identity** with custom `ApplicationUser`
- Role-based access control (Admin, Sales, Production, Logistics, Supplier, etc.)
- Admin area with user management

### 🌍 Localization
- Full **English** and **Turkish** (en-US / tr-TR) support
- Shared resource files for view and data annotation localization
- Language switcher in the UI

### Other Features
- File upload support via **Azure Blob Storage**
- One-click Excel export on listing pages
- Flexible date-time values regarding the region

---

## 🏗️ Architecture

```
Box2Erp-Stage-1/
├── Areas/
│   ├── Admin/              # Admin panel (user management)
│   └── Identity/           # Customized Identity UI (login, register)
├── Controllers/            # 16 MVC controllers
├── Data/
│   ├── AppDbContext.cs      # EF Core DbContext with PostgreSQL
│   └── Constants/           # Application constants
├── Extensions/
│   ├── DateExtensions.cs
│   ├── DateTimeExtensions.cs
│   ├── ExcelExportExtensions.cs
│   ├── OrderQueryExtensions.cs
│   └── ...
├── Filters/                # Action filters (e.g., SupplierRestrictionFilter)
├── Helpers/                # Utility helpers
├── Migrations/             # EF Core migrations
├── ModelBinders/           # Custom model binders (string trimming)
├── Models/
│   ├── Enums/              # OrderStatus, ShipmentType, ProductCategory, etc.
│   ├── ViewModel/          # 17 view models
├── Resources/              # Localization .resx files (EN & TR)
├── Services/
├── Views/                  # 16 view folders + shared layouts
├── wwwroot/                # Static assets & file uploads
└── Program.cs              # Application entry point & DI configuration
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Framework** | ASP.NET Core 9 MVC |
| **Language** | C# 13 |
| **Database** | PostgreSQL (via Npgsql) |
| **ORM** | Entity Framework Core 9 |
| **Authentication** | ASP.NET Core Identity |
| **Cloud Storage** | Azure Blob Storage |
| **Excel Export** | ClosedXML |
| **Charts** | Chart.js |
| **Frontend** | Bootstrap, jQuery, Razor Views |
| **Localization** | .resx resource files (EN / TR) |

---

## 🔧 Configuration

### Connection Retry
PostgreSQL connections are configured with automatic retry on failure:
- **Max retries:** 5
- **Max delay:** 10 seconds

### Localization
Supported cultures: `en-US` (default), `tr-TR`. Switch languages through the in-app language selector.

### Identity
- Email confirmation is **disabled** by default
- Unique email is **not required** by default
- Custom string-trimming model binder automatically trims whitespace from form inputs

---

<p align="center">
  Built with ❤️ using <strong>ASP.NET Core 9</strong>
</p>

