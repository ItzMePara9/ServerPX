# ☁️ ServerPX

### Modern Proxmox Virtualization & Hosting Management Platform

**ServerPX** is a modern, self-hosted virtualization management platform designed for VPS hosting providers. Built around Proxmox VE, ServerPX aims to simplify virtual machine provisioning, infrastructure management, user administration, and resource allocation through a clean, professional web interface.

Inspired by the functionality of modern hosting panels, ServerPX combines an original user experience with powerful infrastructure management capabilities.

> **Project status:** Under development. Features described below represent the project vision and may not yet be implemented.

---

## ✨ Features

### 🖥️ Virtual Machine Management
- Create and manage virtual machines through Proxmox VE.
- Provision instances using approved operating system images and templates.
- Configure CPU, RAM, disk, and networking.
- Start, stop, restart, and manage virtual machines.
- View instance status and resource usage.
- Track provisioning tasks and operation results.

### 📦 Container Management
- Manage Proxmox containers (CTs).
- Create containers from supported templates.
- Configure container resources and networking.
- Manage container lifecycle operations.

### 🌐 Node Management
- Connect Proxmox nodes through the administration panel.
- Monitor node availability and health.
- View CPU, RAM, and storage utilization.
- Organize nodes into locations.
- Configure node eligibility for automatic provisioning.

### 👥 User Management
- User registration and authentication.
- Role-based access control.
- User-specific virtual machine management.
- Configurable resource quotas.
- Account administration and activity tracking.

### 🔐 Authentication
- Email and password authentication.
- GitHub OAuth login and registration.
- Google OAuth login and registration.
- Secure session management.
- Configurable registration policies.
- Password recovery and email verification where configured.

### ⚙️ Administration Panel
- Centralized infrastructure management.
- Manage users, nodes, locations, and templates.
- Configure resource limits and provisioning policies.
- Customize company name, logo, and platform branding.
- Monitor infrastructure and provisioning activity.
- Configure global application settings.

### 📊 Resource Monitoring
- CPU utilization.
- RAM usage.
- Storage utilization.
- VM and CT counts.
- Node capacity and availability.
- Circular resource indicators and dashboard statistics.

Resource information is intended to come from the actual backend and connected Proxmox infrastructure.

### 🔄 Automatic Node Allocation
Configure how new virtual machines are assigned to eligible nodes:

- **Round Robin:** Rotate placement across eligible nodes.
- **Least Used:** Prefer nodes with lower resource utilization.
- **Manual Selection:** Choose a node explicitly.

Allocation must account for node health, available capacity, and configured resource limits.

### 🎨 Modern UI/UX
- Clean, professional dashboard.
- Original ServerPX branding.
- Dark and light themes.
- Responsive layouts.
- Interactive charts and resource indicators.
- Organized navigation and management tables.
- Loading states, notifications, and confirmation dialogs.

---

## 🏗️ Architecture

ServerPX is designed around three primary components:

| Component | Responsibility |
|---|---|
| Client Panel | User accounts, VM provisioning, and instance management |
| Admin Panel | Infrastructure, users, locations, templates, and platform settings |
| Backend Services | Authentication, database operations, scheduling, and Proxmox API integration |

The backend communicates with Proxmox VE to perform authorized infrastructure operations. Sensitive credentials remain server-side.

---

## 🔌 Proxmox VE Integration

ServerPX is designed to use the Proxmox VE API for real virtualization management.

Initial connection settings can be configured using environment variables.

Example `.env` configuration:

```env
APP_NAME=ServerPX
APP_ENV=production
APP_URL=https://panel.example.com
APP_SECRET=replace_with_a_secure_random_secret

DATABASE_URL=your_database_connection_string

PROXMOX_ENABLED=true
PROXMOX_API_URL=https://proxmox.example.com:8006/api2/json
PROXMOX_DEFAULT_NODE=
PROXMOX_AUTH_MODE=token
PROXMOX_TOKEN_ID=
PROXMOX_TOKEN_SECRET=
PROXMOX_VERIFY_TLS=true

GITHUB_CLIENT_ID=
GITHUB_CLIENT_SECRET=
GITHUB_CALLBACK_URL=https://panel.example.com/auth/github/callback

GOOGLE_CLIENT_ID=
GOOGLE_CLIENT_SECRET=
GOOGLE_CALLBACK_URL=https://panel.example.com/auth/google/callback
```

The actual variable names and setup requirements depend on the implementation.

### Security Notes
- Never commit `.env` files or real credentials to GitHub.
- Use appropriately restricted Proxmox API credentials.
- Keep privileged API operations on the backend.
- Validate TLS certificates in production.
- Enforce authorization and resource limits server-side.

---

## 🗂️ Planned Admin Sections

| Section | Purpose |
|---|---|
| Dashboard | Infrastructure overview and resource statistics |
| Virtual Machines | Manage KVM virtual machines |
| Containers | Manage Proxmox containers |
| Nodes | Configure and monitor virtualization nodes |
| Users | Manage accounts, roles, and quotas |
| Locations | Organize infrastructure geographically |
| Templates | Manage available operating systems and templates |
| Plans | Configure resource packages and limits |
| Tasks | Track provisioning operations |
| Settings | Configure branding, authentication, and platform behavior |

---

## 🚀 Project Goals

ServerPX aims to provide hosting providers with:

- A centralized virtualization management platform.
- A straightforward customer experience.
- Automated VM provisioning.
- Flexible infrastructure organization.
- Configurable resource allocation.
- Secure administration and access control.
- An extensible foundation for future hosting features.

The goal is to make infrastructure management easier while keeping the platform maintainable, secure, and customizable.

---

## 🛠️ Technology Stack

The final technology stack will follow the existing project implementation.

Planned integrations include:

- **Virtualization:** Proxmox VE
- **Authentication:** Email/password, GitHub OAuth, and Google OAuth
- **Configuration:** Environment variables and administrative settings
- **Database:** Persistent relational database
- **Background processing:** Provisioning jobs and task tracking
- **Frontend:** Modern, responsive web interface

---

## 📋 Development Roadmap

- [ ] Establish application architecture and database schema.
- [ ] Implement authentication and session management.
- [ ] Add GitHub and Google OAuth.
- [ ] Integrate the Proxmox VE API.
- [ ] Implement node management and connectivity checks.
- [ ] Build VM provisioning and lifecycle operations.
- [ ] Add container management.
- [ ] Implement template management.
- [ ] Build user, role, and quota management.
- [ ] Add locations and resource allocation policies.
- [ ] Implement round-robin scheduling.
- [ ] Build the administration dashboard.
- [ ] Add branding and global settings.
- [ ] Implement audit logs and background task tracking.
- [ ] Add automated tests and deployment documentation.

---

## 🔒 Security

ServerPX is intended to manage real infrastructure, so security is a core design requirement.

The implementation should include:

- Server-side authorization checks.
- Secure password hashing and session handling.
- Protected OAuth flows.
- Restricted Proxmox API permissions.
- Input validation and resource quota enforcement.
- Secure credential storage.
- Audit logging for sensitive operations.
- Safe handling of failed provisioning requests.

Never expose privileged Proxmox credentials to the browser.

---

## 🤝 Contributing

Contributions, suggestions, bug reports, and feature requests are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Implement and test the changes.
4. Submit a pull request with a clear description.

Please report security vulnerabilities privately rather than publishing exploit details in public issues.

---

## 📜 License

A license has not yet been specified. Add an appropriate `LICENSE` file before distributing or accepting contributions under particular licensing terms.

---

## 💙 Credits

Developed as an independent project to explore modern virtualization management, automated provisioning, and self-hosted infrastructure tooling.

**ServerPX — Your Infrastructure. Your Control.** ☁️

