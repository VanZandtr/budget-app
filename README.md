# Monthly Budget Tracker

A simple, responsive web app to track your monthly budget with custom categories and expenses.

## Features

- Set monthly income with easy edit option
- Create custom budget categories with visual progress bars
- Add recurring expenses that auto-deduct from your budget
- Track one-time expenses with descriptions and amounts
- Smart budget calculation - category budgets immediately deduct from remaining budget
- Real-time budget calculations and visual feedback
- Reset individual categories or clear the entire budget
- Firebase database integration for sharing between devices
- Simple 3-step workflow for shared budgets
- Data persistence using both cloud and local storage
- Responsive design for mobile and desktop
- Visual indicators for budget status

## How to Use

### Basic Budget Management
1. **Set Your Income**: Enter your monthly income and click "Set Income" (click the pencil icon to edit later)
2. **Add Recurring Expenses**: Add fixed monthly expenses like rent or subscriptions that automatically deduct from your budget
3. **Add Categories**: Create budget categories like "Groceries", "Entertainment", etc. with monthly budget amounts
4. **Track Expenses**: Add expenses to each category with descriptions and amounts
5. **Monitor Budget**: Watch your remaining budget update in real-time with visual progress bars

### Sharing Between Devices (or with Family)
1. **Step 1: Get Latest Budget**: First check connection, then pull the latest budget from the database
2. **Step 2: Update Budget**: Make your changes to recurring expenses and categories
3. **Step 3: Save Your Changes**: Push your updated budget back to the database

Both users should follow these three steps to avoid conflicts. Always pull before making changes!

## Hosting on GitHub Pages

Follow these steps to host your budget app on GitHub Pages:

### Step 1: Create a GitHub Repository
1. Go to [GitHub.com](https://github.com) and sign in
2. Click the "+" icon in the top right corner
3. Select "New repository"
4. Name your repository `budget-app` (or any name you prefer)
5. Make sure it's set to "Public"
6. Check "Add a README file"
7. Click "Create repository"

### Step 2: Upload Your Files
1. In your new repository, click "uploading an existing file"
2. Drag and drop both `index.html` and `README.md` from your local folder
3. Write a commit message like "Initial budget app upload"
4. Click "Commit changes"

### Step 3: Enable GitHub Pages
1. In your repository, click on "Settings" tab
2. Scroll down to "Pages" in the left sidebar
3. Under "Source", select "Deploy from a branch"
4. Choose "main" branch and "/ (root)" folder
5. Click "Save"

### Step 4: Access Your App
1. GitHub will provide a URL like: `https://yourusername.github.io/budget-app`
2. It may take a few minutes to become available
3. Your app will be live and accessible to anyone with the link!

## Local Development

To run locally, simply open `index.html` in any modern web browser.

## Firebase Setup

### Step 1: Create a Firebase Project
1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Click "Add project"
3. Enter a project name (e.g., "Budget Tracker")
4. Follow the setup wizard

### Step 2: Set Up Firestore Database
1. In the left sidebar, click "Firestore Database"
2. Click "Create database"
3. Choose "Start in production mode"
4. Select a location closest to you
5. Click "Enable"

### Step 3: Set Security Rules
1. Go to the "Rules" tab in Firestore
2. Use these rules for simple access:
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /budgets/{budgetId} {
      allow read, write: if true;
    }
  }
}
```

### Step 4: Get Your Firebase Config
1. Click the gear icon (⚙️) and select "Project settings"
2. Scroll down to "Your apps" and click the web icon (</>) 
3. Register your app with a nickname
4. Copy the Firebase configuration object
5. Replace the config in your index.html file

## Browser Compatibility

Works in all modern browsers including Chrome, Firefox, Safari, and Edge.

## Version History

- **v2.1.0**: Enhanced mobile responsiveness with improved touch targets and layout
- **v2.0.0**: Major UI redesign with 3-step workflow for shared budgets
- **v1.9.0**: Reorganized workflow into clear steps
- **v1.8.0**: Simplified sync interface
- **v1.7.0**: Removed URL sharing in favor of Firebase database
- **v1.6.0**: Added Firebase database integration
- **v1.5.0**: Added ownership verification for shared budgets
- **v1.4.0**: Improved budget calculation - category budgets immediately deduct from remaining budget
- **v1.3.0**: Added data compression for URL sharing to reduce URL length
- **v1.2.1**: Added URL character count warning
- **v1.2.0**: Added budget progress bars and UI improvements
- **v1.1.0**: Added recurring expenses and application reset
- **v1.0.0**: Initial release with basic budget tracking