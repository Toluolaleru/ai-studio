# 🚀 Quick Reference Card

## Where to Find Things

### 🎯 View Model Spend
**Settings → Usage & Billing**

Shows:
- Current spend: **$47.32 / $100.00**
- Total requests: **1,247**
- Charts, breakdowns, billing history

---

### 👥 Manage Teams
**Profile Dropdown (top-right avatar)**

Actions:
- See all teams
- Switch teams (click to activate)
- Create new team (+ button)

---

### 📧 Invite Members
**Settings → Members** (teams only)

Actions:
- Invite with email + role
- Change roles (⋮ menu)
- Remove members

---

## 📊 Usage & Billing Overview

### Top Stats
| Metric | Value | Color |
|--------|-------|-------|
| Current Spend | $47.32 | Blue gradient |
| Total Requests | 1,247 | White |
| Avg/Request | $0.038 | White |
| Spending Limit | $100.00 | White |

### Charts
1. **Spending Trends** (Line chart)
   - Blue: Image Generation
   - Purple: Video Generation
   - Light Purple: Image Editing
   - Toggle: 7D / 30D / 90D

2. **Cost Distribution** (Pie chart)
   - Same 3 model types
   - Donut style

### Model Details
| Model | Requests | Cost | $/req |
|-------|----------|------|-------|
| Image Gen | 542 | $31.20 | $0.0576 |
| Video Gen | 423 | $23.80 | $0.0563 |
| Image Edit | 282 | $9.40 | $0.0333 |

### Billing History
- Jan 2026: $47.32 (Current)
- Dec 2025: $52.18 (Paid)
- Nov 2025: $38.54 (Paid)

---

## 🎨 Color Codes

```
Primary Blue:    #0000FF
Secondary:       #5865f2
Light Purple:    #8B92FF
Success Green:   #10b981
Warning Orange:  #f59e0b
Error Red:       #dc2626
```

---

## 📁 File Locations

```
Components:
/src/app/components/usage-billing.tsx   ⭐ NEW
/src/app/components/dashboard.tsx       ⭐ UPDATED
/src/app/components/settings.tsx        ⭐ UPDATED
/src/app/components/team-members.tsx
/src/app/components/create-team-modal.tsx
/src/app/components/invite-member-modal.tsx

Docs:
/WALKTHROUGH.md                    Complete guide
/USAGE_BILLING_GUIDE.md           Feature docs
/TESTING_USAGE_BILLING.md         Test checklist
/ARCHITECTURE_OVERVIEW.md         System design
```

---

## 🔄 Quick Workflows

### Create Team
1. Avatar → Create New Team
2. Enter name + description
3. Create → Auto-switched ✓

### Invite Member
1. Settings → Members
2. Invite Member button
3. Email + Role → Send ✓

### View Usage
1. Settings → Usage & Billing
2. See charts and stats ✓

---

## ⚡ Keyboard Shortcuts (Future)

```
Currently: Click-based navigation
Future:
- Cmd+K: Quick search
- Cmd+S: Open settings
- Cmd+T: Create team
- Cmd+I: Invite member
- Cmd+U: View usage
```

---

## 🧪 Testing

**Quick Test**:
1. Create team ✓
2. Check profile dropdown ✓
3. Invite member ✓
4. View usage billing ✓

**Full Test**: See `/TESTING_USAGE_BILLING.md`

---

## 🎯 What's New? ⭐

### Profile Dropdown
- ✅ Shows ALL teams (not just "Personal")
- ✅ Dynamic team list
- ✅ Active team indicator (✓)
- ✅ Click to switch

### Usage & Billing Tab
- ✅ 4 stat cards
- ✅ Line chart (spending trends)
- ✅ Pie chart (cost distribution)
- ✅ 3 model usage cards
- ✅ Billing history table
- ✅ Export button (UI ready)

---

## 📞 Need Help?

**Documentation**:
- User Guide: `/WALKTHROUGH.md`
- Testing: `/TESTING_USAGE_BILLING.md`
- Architecture: `/ARCHITECTURE_OVERVIEW.md`

**Code**:
- Main component: `/src/app/components/usage-billing.tsx`
- Integration: `/src/app/components/settings.tsx`

---

## ✅ Checklist: Is It Working?

- [ ] Profile dropdown shows created teams
- [ ] Can switch between teams
- [ ] Settings → Members shows team members
- [ ] Settings → Usage & Billing shows charts
- [ ] All 4 stat cards display
- [ ] Both charts render
- [ ] Model cards show progress bars
- [ ] Billing table has 3 rows
- [ ] No console errors

**All checked?** You're good to go! 🎉

---

## 🚀 Next Steps

1. **Test the flow** (see WALKTHROUGH.md)
2. **Review usage analytics** (Settings → Usage & Billing)
3. **Connect backend** (when ready)
4. **Deploy** 🚀

---

## 💡 Pro Tips

- Usage data is **mock** (frontend-only for now)
- Team switching updates entire context
- Members tab only appears for teams
- Usage & Billing always available
- Export button ready for backend integration

---

*Last updated: February 4, 2026*
*GenFlow.ai Team Management & Usage Tracking*
