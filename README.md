# Monthly Budget Tracker

A simple, responsive web app to track your monthly budget with custom categories and expenses.

## Features

- Set monthly income with easy edit option
- Create custom budget categories with visual progress bars
- Add recurring expenses that auto-deduct from your budget
- Track one-time expenses with descriptions and amounts
- Real-time budget calculations and visual feedback
- Reset individual categories or the entire application
- Data persistence using browser localStorage
- Share your budget via URL with others
- Responsive design for mobile and desktop
- Visual indicators for budget status

## How to Use

1. **Set Your Income**: Enter your monthly income and click "Set Income" (click the pencil icon to edit later)
2. **Add Recurring Expenses**: Add fixed monthly expenses like rent or subscriptions that automatically deduct from your budget
3. **Add Categories**: Create budget categories like "Groceries", "Entertainment", etc. with monthly budget amounts
4. **Track Expenses**: Add expenses to each category with descriptions and amounts
5. **Monitor Budget**: Watch your remaining budget update in real-time with visual progress bars
6. **Manage Data**: Reset category expenses, delete categories, or reset the entire application
7. **Share Your Budget**: Generate a shareable URL to access your budget on other devices

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

## HTML Structure Demo

Here's a simplified version of the HTML structure for reference:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Monthly Budget Tracker</title>
    <style>
        /* CSS styles here */
        body { font-family: Arial, sans-serif; background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); }
        .container { max-width: 800px; margin: 0 auto; background: white; border-radius: 15px; padding: 30px; }
        /* Additional styles... */
    </style>
</head>
<body>
    <div class="version">v1.2.1</div>
    <div class="container">
        <h1>Monthly Budget Tracker</h1>
        
        <!-- Income Section -->
        <div class="income-section" id="income-section">
            <h3>Monthly Income</h3>
            <div>
                <input type="number" id="income-input" placeholder="Enter monthly income">
                <button onclick="setIncome()">Set Income</button>
            </div>
        </div>
        
        <!-- Budget Summary -->
        <div class="budget-summary">
            <div class="summary-card income-card">
                <h3>Monthly Income <button id="edit-income-btn" onclick="showIncomeSection()">✎</button></h3>
                <div id="total-income">$0.00</div>
            </div>
            <div class="summary-card spent-card">
                <h3>Total Spent</h3>
                <div id="total-spent">$0.00</div>
            </div>
            <div class="summary-card remaining-card">
                <h3>Remaining</h3>
                <div id="remaining-budget">$0.00</div>
            </div>
        </div>
        
        <!-- Recurring Expenses -->
        <div class="recurring-section">
            <h3>Recurring Expenses</h3>
            <div>
                <input type="text" id="recurring-desc-input" placeholder="Description">
                <input type="number" id="recurring-amount-input" placeholder="Monthly amount">
                <button onclick="addRecurringExpense()">Add Recurring Expense</button>
            </div>
            <div id="recurring-expenses" class="expenses"></div>
        </div>
        
        <!-- Budget Categories -->
        <div class="category-section">
            <h3>Budget Categories</h3>
            <div class="add-category">
                <input type="text" id="category-input" placeholder="Category name">
                <input type="number" id="budget-input" placeholder="Monthly budget">
                <button onclick="addCategory()">Add Category</button>
            </div>
            <div id="categories" class="categories"></div>
        </div>
        
        <!-- Share Section -->
        <div class="share-section">
            <h3>Share Your Budget</h3>
            <button onclick="generateShareURL()">Generate Share URL</button>
            <input type="text" id="share-url" readonly>
            <small id="url-char-count"></small>
        </div>
        
        <!-- Reset Section -->
        <div class="reset-section">
            <h3>Reset Application</h3>
            <button class="danger-btn" onclick="resetApplication()">Reset Application</button>
        </div>
    </div>

    <script>
        // JavaScript code here
        let monthlyIncome = 0;
        let categories = {};
        let recurringExpenses = [];
        
        // Core functions: setIncome, addCategory, addRecurringExpense, etc.
        
        // Load data on page load
        window.onload = function() {
            loadData();
        };
    </script>
</body>
</html>
```

## Browser Compatibility

Works in all modern browsers including Chrome, Firefox, Safari, and Edge.

## Version History

- **v1.2.1**: Added URL character count warning
- **v1.2.0**: Added budget progress bars and UI improvements
- **v1.1.0**: Added recurring expenses and application reset
- **v1.0.0**: Initial release with basic budget tracking