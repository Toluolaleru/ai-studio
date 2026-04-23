# Usage & Billing Feature Guide

## Overview
A comprehensive model spend tracking system that allows users to monitor their AI usage costs, request volumes, and billing history.

## How to Access
1. Click **Settings** in the profile dropdown or sidebar
2. Click **Usage & Billing** in the left sidebar under "Workspace Settings"

## Features

### 📊 Dashboard Stats (Top Cards)
- **Current Month Spend**: Shows total spend with progress bar vs. limit
- **Total Requests**: All API requests made this month
- **Avg Cost per Request**: Average cost across all models
- **Spending Limit**: Monthly budget with remaining balance

### 📈 Interactive Charts

#### Spending Trends Chart
- **Line chart** showing daily spending breakdown
- **3 model types** tracked:
  - Image Generation (Blue #0000FF)
  - Video Generation (Purple #5865f2)
  - Image Editing (Light Purple #8B92FF)
- **Time periods**: Toggle between 7D, 30D, 90D views

#### Cost Distribution (Pie Chart)
- Visual breakdown of costs by model type
- Shows percentage and dollar amount per model

### 📋 Model Usage Details
Interactive cards for each model showing:
- Total requests
- Total cost
- Cost per request
- Visual progress bar

### 🧾 Billing History Table
- **Period**: Month/year of billing cycle
- **Requests**: Total API calls
- **Amount**: Total cost
- **Status**: Current/Paid
- **Invoice**: View/Download links

## Mock Data Structure

### Current Metrics
```javascript
currentMonthSpend: $47.32
lastMonthSpend: $52.18
spendingLimit: $100.00
totalRequests: 1,247
avgCostPerRequest: $0.038
```

### Model Breakdown
```javascript
Image Generation: 542 requests, $31.20
Video Generation: 423 requests, $23.80
Image Editing: 282 requests, $9.40
```

## Design System
- **Primary Color**: #0000FF (matching GenFlow.ai brand)
- **Charts**: Recharts library with custom blue color scheme
- **Icons**: Lucide React (DollarSign, TrendingUp, Calendar, etc.)
- **Layout**: Responsive grid with max-width container

## Components

### Main Component
- **File**: `/src/app/components/usage-billing.tsx`
- **Export**: `UsageBilling` (no props required)

### Integration
- Added to Settings page as new tab
- Added BarChart3 icon to sidebar
- Accessible from all workspaces (personal & teams)

## Future Enhancements (Backend Integration)
When connecting to a real backend, replace mock data with:
1. Real-time usage metrics from API
2. Historical data from database
3. Actual billing records
4. User-configurable spending limits
5. Export functionality for reports
6. Email alerts for spending thresholds

## Testing Checklist
- [ ] Settings → Usage & Billing tab loads
- [ ] All 4 stat cards display correctly
- [ ] Line chart renders with 3 model types
- [ ] Pie chart shows cost distribution
- [ ] Model usage cards show progress bars
- [ ] Billing history table displays 3 months
- [ ] Toggle between 7D/30D/90D periods
- [ ] Responsive on different screen sizes
- [ ] Export button is visible (placeholder)
- [ ] "Near limit" warning shows at >80% spend

## Color Reference
```css
Primary Blue: #0000FF
Secondary Purple: #5865f2
Light Purple: #8B92FF
Success Green: #10b981
Warning Orange: #f59e0b
Error Red: #dc2626
```

## Notes
- All data is currently **mock/frontend-only**
- No backend API calls are made
- Perfect for demos and UI testing
- Ready to connect to real usage tracking API
