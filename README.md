# Client Intake Form Module

## Overview

The **Client Intake Form Module** is a feature-rich component of an internal ERP system. It enables users to log in using their Microsoft accounts via MSAL (Microsoft Authentication Library) and fill out client intake forms through a multi-section interface. The module leverages a modern tech stack, including Vite, TypeScript, Vue 3, Vue Router, Pinia, and Microsoft Graph services, for seamless functionality and a robust user experience.

---

## Features

1. **Microsoft Account Integration**  
   - User authentication is managed using MSAL, allowing seamless sign-in with Microsoft accounts.
   - Access to user details through Microsoft Graph API.

2. **Multi-Section Form Navigation**  
   - The client intake form is divided into 4 sections for better user experience.
   - Navigation between sections is handled by Vue Router 4.

3. **Real-Time Data Management**  
   - Pinia store is used to manage login state, user data, and client intake information.
   - Live updates to form fields for a smooth editing experience.

4. **Save and Update Functionality**  
   - Users can save partially completed forms or update existing client intake records.
   - AJAX calls are used to interact with a FastAPI backend for saving and retrieving data.

5. **Notifications**  
   - Toast notifications are provided for key events such as successful save/update or errors, using a toaster add-on.

6. **API Integration**  
   - The module is connected to an API endpoint configured on Microsoft Azure for backend services.

---

## Technology Stack

### Frontend
- **Vite**: For fast development and optimized production builds.
- **TypeScript**: Strongly typed language for improved maintainability.
- **Vue 3**: Progressive JavaScript framework for building user interfaces.
- **Vue Router 4**: For multi-section form navigation.
- **Pinia**: For state management, ensuring consistent data flow and live updates.

### Authentication & APIs
- **MSAL (Microsoft Authentication Library)**: For user authentication.
- **Microsoft Graph Services**: To fetch user details and interact with Microsoft services.
- **FastAPI**: Backend API for form data processing.

### Utilities
- **ESLint**: For maintaining code quality and enforcing consistent coding standards.
- **Toaster Add-On**: For non-intrusive user notifications.

---

## Installation and Setup

### Prerequisites
- Node.js and npm installed on your system.
- Azure AD App Registration set up for MSAL authentication.

### Steps
1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd client-intake-form
   ```

2. **Install Dependencies**
   ```bash
   npm install
   ```

3. **Environment Configuration**
   - Create a `.env` file in the root directory.
   - Add the following environment variables:
     ```env
     VITE_AZURE_CLIENT_ID=<Azure App Client ID>
     VITE_AZURE_TENANT_ID=<Azure Tenant ID>
     VITE_API_BASE_URL=<API Base URL>
     ```

4. **Run the Application**
   ```bash
   npm run dev
   ```

---

## Usage

### Authentication
1. Navigate to the login page.
2. Use your Microsoft account credentials to sign in.
3. On successful login, user data will be stored in the Pinia store.

### Form Navigation
- Use the tabs or navigation buttons to move between the four sections of the form.

### Saving Data
- Click the **Save** button to save your progress.
- Use the **Update** button to modify existing records.

### Notifications
- Toast notifications will confirm the success or failure of save/update actions.

---

## Folder Structure

```plaintext
src/
├── components/           # Reusable Vue components
├── pages/                # Form sections and views
├── router/               # Vue Router configuration
├── store/                # Pinia store for state management
├── services/             # API and MSAL service integrations
├── assets/               # Static assets like images or styles
├── utils/                # Utility functions
├── App.vue               # Root component
├── main.ts               # Entry point
```

---

## Development Notes

### MSAL Configuration
- The MSAL library is initialized in the `services/msal.ts` file.
- Scopes include `User.Read` for fetching basic user profile data via Microsoft Graph.

### API Endpoints
- The application interacts with FastAPI endpoints hosted on Microsoft Azure.
- AJAX calls are implemented in the `services/api.ts` file for cleaner separation of concerns.

### Notifications
- The toaster add-on is configured in `utils/notifications.ts` for easy use across the application.

---

## Contributing

1. Fork the repository and create a new branch.
2. Make your changes and ensure the code passes ESLint checks.
3. Submit a pull request for review.

---

## License

This project is proprietary and intended for internal use only. All rights reserved.
