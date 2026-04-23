# 🧪 Usage & Billing Testing Checklist

## Pre-Test Setup
- [ ] App is running
- [ ] You're logged in
- [ ] At least one team is created (from previous testing)

---

## 🎯 Test 1: Access Usage & Billing

### From Personal Workspace
1. [ ] Click profile dropdown
2. [ ] Click "Personal" workspace (if not active)
3. [ ] Click "Settings" in dropdown
4. [ ] Click "Usage & Billing" in left sidebar
5. [ ] **Expected**: Dashboard loads with charts and data

### From Team Workspace
1. [ ] Click profile dropdown
2. [ ] Switch to a team workspace
3. [ ] Go to Settings
4. [ ] Click "Usage & Billing"
5. [ ] **Expected**: Same dashboard (usage is global)

---

## 📊 Test 2: Stats Cards

### Card 1: Current Month Spend
- [ ] Shows dollar amount: **$47.32**
- [ ] Shows "This month" badge
- [ ] Progress bar is visible
- [ ] Shows percentage: **47%**
- [ ] Gradient background (blue to purple)

### Card 2: Total Requests
- [ ] Shows: **1,247** requests
- [ ] Shows green up arrow (TrendingUp)
- [ ] Shows: **+12% from last month**
- [ ] White background with border

### Card 3: Avg Cost/Request
- [ ] Shows: **$0.038**
- [ ] Shows "Avg cost/request" label
- [ ] Shows "Across all models" subtext
- [ ] White background with border

### Card 4: Spending Limit
- [ ] Shows: **$100.00**
- [ ] Shows "Monthly limit" label
- [ ] Shows remaining: **$52.68**
- [ ] **If >80% spent**: Shows orange "Near limit" badge
- [ ] White background with border

---

## 📈 Test 3: Spending Trends Chart

### Chart Rendering
- [ ] Chart loads without errors
- [ ] Line chart is visible
- [ ] 3 lines are displayed (blue, purple, light purple)
- [ ] X-axis shows dates (Jan 1, Jan 5, etc.)
- [ ] Y-axis shows dollar amounts ($12, $24, etc.)

### Interactive Features
- [ ] Hover over any point → Tooltip appears
- [ ] Tooltip shows exact dollar amount
- [ ] Tooltip shows all 3 model values
- [ ] Legend shows at bottom:
  - [ ] Image Generation (blue circle)
  - [ ] Video Generation (purple circle)
  - [ ] Image Editing (light purple circle)

### Time Period Toggles
- [ ] Three buttons visible: **7D**, **30D**, **90D**
- [ ] **30D** is active by default (blue background)
- [ ] Click **7D** → Button turns blue
- [ ] Click **90D** → Button turns blue
- [ ] Click back to **30D** → Returns to blue
- [ ] **Note**: Chart data doesn't change (mock data), but button state does

---

## 🥧 Test 4: Cost Distribution Chart

### Pie Chart
- [ ] Donut chart is visible
- [ ] 3 segments displayed:
  - [ ] Blue segment (largest)
  - [ ] Purple segment (medium)
  - [ ] Light purple segment (smallest)
- [ ] Hover over segment → Tooltip shows cost
- [ ] Center is hollow (donut style)

### Legend Below Chart
- [ ] 3 rows displayed
- [ ] Each row has:
  - [ ] Colored dot matching chart
  - [ ] Model name
  - [ ] Dollar amount
- [ ] Row 1: Image Generation - **$31.20**
- [ ] Row 2: Video Generation - **$23.80**
- [ ] Row 3: Image Editing - **$9.40**

---

## 📋 Test 5: Model Usage Details

### Section Header
- [ ] Title: "Model Usage Details"
- [ ] Subtitle: "Request volume and costs by model"
- [ ] Export button visible (top-right)
- [ ] Export button shows download icon

### Card 1: Image Generation
- [ ] Blue icon background
- [ ] Image icon displayed
- [ ] Title: "Image Generation"
- [ ] Requests: **542 requests**
- [ ] Cost: **$31.20**
- [ ] Per-request: **$0.0576/req**
- [ ] Progress bar: **66% width** (blue)
- [ ] Hover → Light gray background

### Card 2: Video Generation
- [ ] Purple icon background
- [ ] Video icon displayed
- [ ] Title: "Video Generation"
- [ ] Requests: **423 requests**
- [ ] Cost: **$23.80**
- [ ] Per-request: **$0.0563/req**
- [ ] Progress bar: **50% width** (purple)
- [ ] Hover → Light gray background

### Card 3: Image Editing
- [ ] Light purple icon background
- [ ] Sparkles icon displayed
- [ ] Title: "Image Editing"
- [ ] Requests: **282 requests**
- [ ] Cost: **$9.40**
- [ ] Per-request: **$0.0333/req**
- [ ] Progress bar: **20% width** (light purple)
- [ ] Hover → Light gray background

---

## 🧾 Test 6: Billing History Table

### Table Structure
- [ ] Table header with 5 columns:
  - [ ] Period
  - [ ] Requests
  - [ ] Amount
  - [ ] Status
  - [ ] Invoice

### Row 1: Current Month
- [ ] Period: **January 2026**
- [ ] Requests: **1,247**
- [ ] Amount: **$47.32**
- [ ] Status: **Current** (blue badge)
- [ ] Invoice: **View** (blue link)
- [ ] Hover → Light gray background

### Row 2: Last Month
- [ ] Period: **December 2025**
- [ ] Requests: **1,108**
- [ ] Amount: **$52.18**
- [ ] Status: **Paid** (green badge)
- [ ] Invoice: **Download** (blue link)
- [ ] Hover → Light gray background

### Row 3: Two Months Ago
- [ ] Period: **November 2025**
- [ ] Requests: **892**
- [ ] Amount: **$38.54**
- [ ] Status: **Paid** (green badge)
- [ ] Invoice: **Download** (blue link)
- [ ] Hover → Light gray background

---

## 🎨 Test 7: Visual Design

### Color Scheme
- [ ] Primary actions use **#0000FF** (blue)
- [ ] Charts use blue/purple palette
- [ ] Consistent spacing between elements
- [ ] All borders are **#e0e0e0** (light gray)

### Typography
- [ ] Headers are bold and readable
- [ ] Stats are large and prominent
- [ ] Small text is **13px** or **14px**
- [ ] Consistent font (Space Grotesk)

### Layout
- [ ] Page is centered with max-width
- [ ] Padding around all sections
- [ ] Cards have proper spacing
- [ ] Charts are not cut off
- [ ] Scrollbar appears if needed

---

## 📱 Test 8: Responsive Design

### Desktop (Full Width)
- [ ] All 4 stat cards in one row
- [ ] Chart + Pie chart side-by-side
- [ ] Table shows all columns
- [ ] No horizontal scrolling

### Tablet (Medium Width)
- [ ] Stat cards: 2x2 grid
- [ ] Charts stack vertically
- [ ] Table is scrollable horizontally
- [ ] Content remains readable

### Mobile (Small Width)
- [ ] Stat cards: 1 column
- [ ] Charts: 1 column
- [ ] Table: Horizontal scroll
- [ ] All content accessible

---

## 🔄 Test 9: Navigation

### From Other Pages
1. [ ] From Homepage → Settings → Usage & Billing ✓
2. [ ] From Image Playground → Settings → Usage & Billing ✓
3. [ ] From Asset Library → Settings → Usage & Billing ✓
4. [ ] From Members tab → Usage & Billing tab ✓

### Back Navigation
1. [ ] Click "Back" arrow → Returns to previous page ✓
2. [ ] Click "Home" in sidebar → Goes to homepage ✓
3. [ ] Active tab stays highlighted ✓

---

## 🚨 Test 10: Edge Cases

### No Data State (Currently Not Implemented)
- [ ] **Future**: Should show empty state message
- [ ] **Current**: Always shows mock data ✓

### Error State (Currently Not Implemented)
- [ ] **Future**: Should show error message if API fails
- [ ] **Current**: No errors (frontend-only) ✓

### Loading State (Currently Not Implemented)
- [ ] **Future**: Should show skeleton/spinner
- [ ] **Current**: Renders immediately ✓

---

## ✅ Success Criteria

### Must Pass (Critical)
- [ ] All 4 stat cards display correctly
- [ ] Both charts render without errors
- [ ] All 3 model usage cards show
- [ ] Billing history table has 3 rows
- [ ] No console errors
- [ ] Page is scrollable
- [ ] All hover effects work

### Should Pass (Important)
- [ ] Time period toggles change color
- [ ] Chart tooltips appear on hover
- [ ] Export button is visible
- [ ] Colors match brand (#0000FF)
- [ ] Typography is consistent
- [ ] Spacing looks professional

### Nice to Have (Polish)
- [ ] Smooth transitions
- [ ] Responsive on all screen sizes
- [ ] Links show hover underline
- [ ] Progress bars animate smoothly

---

## 🐛 Known Limitations (Expected)

### Frontend-Only
- ⚠️ Data is mock/static (not from API)
- ⚠️ Export button doesn't download file
- ⚠️ Invoice links don't navigate
- ⚠️ Time period toggle doesn't change data
- ⚠️ No real user-specific data

### These Are OK! 
This is a **frontend-only implementation** for UI/UX testing. Backend integration comes later.

---

## 📝 Bug Report Template

If you find an issue, note:

```
Component: [e.g., Spending Trends Chart]
Issue: [e.g., Chart not rendering]
Steps to Reproduce:
1. Go to Settings
2. Click Usage & Billing
3. ...

Expected: [What should happen]
Actual: [What actually happened]
Browser: [Chrome/Firefox/Safari]
Screenshot: [If applicable]
Console Errors: [Copy any errors]
```

---

## 🎉 All Tests Passed?

If everything checks out:
- ✅ Your usage tracking is fully functional!
- ✅ Ready for demos and presentations
- ✅ Ready for backend integration
- ✅ Complete frontend-only MVP

Next steps:
1. Connect to real usage tracking API
2. Add data export functionality
3. Implement spending alerts
4. Add custom date range picker
5. Create PDF invoice generation

---

## 📚 Related Documentation
- `/USAGE_BILLING_GUIDE.md` - Feature overview
- `/WALKTHROUGH.md` - Complete user journey
- `/src/app/components/usage-billing.tsx` - Source code
