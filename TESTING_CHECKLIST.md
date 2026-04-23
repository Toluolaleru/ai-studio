# Team Management System - Testing Checklist

## ✅ Pre-Flight Check

Before testing, ensure:
- [ ] Profile dropdown in dashboard.tsx (lines 641-709) has been updated with the code from `/dropdown-fix.txt`
- [ ] All three new component files exist:
  - [ ] `/src/app/components/create-team-modal.tsx`
  - [ ] `/src/app/components/invite-member-modal.tsx`
  - [ ] `/src/app/components/team-members.tsx`
- [ ] No TypeScript errors in the console

---

## 🧪 Test Scenarios

### **1. Profile Dropdown - Team Switching**

**Steps:**
1. Click on your profile avatar in the top-right corner
2. Profile dropdown should appear

**Expected Results:**
- [ ] Dropdown shows a backdrop overlay (clicking outside closes dropdown)
- [ ] Dropdown shows your personal workspace at the top
- [ ] Personal workspace has label "personal" (lowercase)
- [ ] Personal workspace has a blue checkmark (it's the current team)
- [ ] "Create New Team" button is visible below
- [ ] Settings and Logout buttons are at the bottom

---

### **2. Create New Team**

**Steps:**
1. Click profile dropdown
2. Click "Create New Team"
3. Modal appears

**Test Modal:**
- [ ] Modal has blue icon (Users icon)
- [ ] Modal has title "Create New Team"
- [ ] Team Name field is required (marked with red asterisk)
- [ ] Description field is optional
- [ ] Info box says "You'll be able to invite team members after creating your team"
- [ ] Cancel button closes modal
- [ ] Create button is disabled when team name is empty

**Create a Team:**
1. Enter team name: "Marketing Team"
2. Enter description: "Content and social media marketing"
3. Click "Create Team"

**Expected Results:**
- [ ] Modal closes
- [ ] Dropdown closes
- [ ] You're now on "Marketing Team" workspace
- [ ] Page doesn't change (still on home)

---

### **3. Verify Team was Created**

**Steps:**
1. Click profile dropdown again

**Expected Results:**
- [ ] Dropdown shows TWO teams now:
  - [ ] Your personal workspace (with "personal" label)
  - [ ] Marketing Team (with "team" label)
- [ ] Marketing Team has the blue checkmark (it's current)
- [ ] Personal workspace does NOT have checkmark

---

### **4. Switch Between Teams**

**Steps:**
1. Click profile dropdown
2. Click on your personal workspace

**Expected Results:**
- [ ] Dropdown closes
- [ ] Personal workspace is now active
- [ ] Click dropdown again - checkmark is on personal workspace

**Switch back:**
1. Click dropdown
2. Click "Marketing Team"

**Expected Results:**
- [ ] Back to Marketing Team
- [ ] Checkmark moves to Marketing Team

---

### **5. Settings - Workspace Display**

**Steps:**
1. While on Marketing Team, click Settings (in sidebar or dropdown)
2. Look at the left sidebar under "Workspace Settings"

**Expected Results:**
- [ ] Workspace selector shows "Marketing Team" name
- [ ] Avatar shows "M" (first letter)
- [ ] A new "Members" menu item appears
- [ ] Members menu has Users icon

**Test Personal Workspace:**
1. Go back to Home (click back arrow)
2. Switch to personal workspace (via profile dropdown)
3. Go to Settings again

**Expected Results:**
- [ ] Workspace selector shows your email username
- [ ] "Members" menu item is HIDDEN (personal workspaces don't have members)

---

### **6. Invite Team Members**

**Steps:**
1. Switch back to Marketing Team
2. Go to Settings
3. Click "Members" in the left sidebar

**Expected Results:**
- [ ] Team Members page appears
- [ ] Header shows "Team Members"
- [ ] Subtitle shows "Marketing Team • 1 member"
- [ ] Blue "Invite Member" button in top right
- [ ] Table shows you as the only member
- [ ] Your entry shows:
  - [ ] Your avatar with initial
  - [ ] Your name and email
  - [ ] Blue "You" badge next to your name
  - [ ] Role badge with crown icon "👑 Owner" (gold/orange badge)
  - [ ] Green dot with "Active" status
  - [ ] No action menu (⋮) - can't modify yourself

**Invite First Member:**
1. Click "Invite Member" button
2. Modal appears

**Test Modal:**
- [ ] Modal shows UserPlus icon
- [ ] Title is "Invite Member"
- [ ] Subtitle shows "Marketing Team"
- [ ] Email field is required
- [ ] Three role options with radio buttons:
  - [ ] Admin - "Can manage team settings and members"
  - [ ] Member - "Can create and edit content" (default selected)
  - [ ] Viewer - "Can only view content"
- [ ] "Member" is selected by default
- [ ] Send Invite button is disabled when email is empty

**Invite Admin:**
1. Enter email: "sarah@company.com"
2. Select "Admin" role
3. Click "Send Invite"

**Expected Results:**
- [ ] Modal closes
- [ ] Members list updates to show 2 members
- [ ] Subtitle shows "Marketing Team • 2 members"
- [ ] New member appears:
  - [ ] Name: "sarah" (from email)
  - [ ] Email: "sarah@company.com"
  - [ ] Role badge: Shield icon "🛡️ Admin" (blue badge)
  - [ ] Status: Clock icon "Pending" (orange/yellow)
  - [ ] Has action menu (⋮)

**Invite More Members:**
1. Click "Invite Member" again
2. Email: "john@company.com"
3. Role: "Member"
4. Click "Send Invite"

**Expected Results:**
- [ ] John added with "Member" role (grey badge)
- [ ] Status: "Pending"
- [ ] Member count: "Marketing Team • 3 members"

**Invite Viewer:**
1. Invite "lisa@company.com" as "Viewer"

**Expected Results:**
- [ ] Lisa added with Eye icon "👁️ Viewer" (grey badge)
- [ ] Status: "Pending"
- [ ] Member count: "Marketing Team • 4 members"

---

### **7. Change Member Roles**

**Steps:**
1. On Sarah (Admin), click the action menu (⋮)

**Expected Results:**
- [ ] Dropdown appears with sections:
  - [ ] "CHANGE ROLE" header (grey, uppercase)
  - [ ] Three role options: Admin, Member, Viewer
  - [ ] Admin has a checkmark (current role)
  - [ ] "Remove Member" button at bottom (red text)

**Change Role:**
1. Click "Member" in the dropdown

**Expected Results:**
- [ ] Dropdown closes
- [ ] Sarah's role badge changes to "Member"
- [ ] Shield icon changes to User icon
- [ ] Badge color changes from blue to grey

**Change Back:**
1. Click ⋮ on Sarah again
2. Select "Admin"

**Expected Results:**
- [ ] Role changes back to Admin
- [ ] Blue shield badge returns

---

### **8. Remove Team Member**

**Steps:**
1. Click ⋮ on Lisa (Viewer)
2. Click "Remove Member"

**Expected Results:**
- [ ] Lisa disappears from the list immediately
- [ ] Member count: "Marketing Team • 3 members"
- [ ] No confirmation dialog (it's frontend-only mock data)

---

### **9. Edge Cases & UI States**

**Test Empty State:**
1. Create a brand new team: "Design Team"
2. Go to Settings → Members

**Expected Results:**
- [ ] Shows only you (owner)
- [ ] Member count: "Design Team • 1 member" (singular)

**Test Scrolling (if you invite many members):**
1. Invite 10+ members to Marketing Team

**Expected Results:**
- [ ] Members table scrolls vertically
- [ ] Header stays fixed
- [ ] All members are accessible

**Test Profile Dropdown Team List:**
1. Create 5+ teams
2. Click profile dropdown

**Expected Results:**
- [ ] Teams section has max-height
- [ ] Teams section scrolls if too many
- [ ] Scrollbar appears when needed
- [ ] All teams are accessible

---

### **10. Settings Tab Switching**

**Steps:**
1. While in Settings on Marketing Team
2. Click "Your Profile" in left sidebar

**Expected Results:**
- [ ] Profile tab becomes active (blue background)
- [ ] Members tab becomes inactive
- [ ] Profile settings content appears:
  - [ ] Email field
  - [ ] Interests section
  - [ ] Delete Account section

**Switch Back:**
1. Click "Members" in left sidebar

**Expected Results:**
- [ ] Members tab becomes active (blue)
- [ ] Team Members page appears
- [ ] All members are still there (state preserved)

---

### **11. Workspace Indicator Updates**

**Steps:**
1. Switch to "Design Team" (via profile dropdown)
2. Go to Settings

**Expected Results:**
- [ ] Workspace selector shows "Design Team" with "D" avatar
- [ ] Members tab shows "Design Team • 1 member"
- [ ] Only you are in the members list

**Switch to Personal:**
1. Go to Home
2. Switch to personal workspace
3. Go to Settings

**Expected Results:**
- [ ] Workspace selector shows your email username
- [ ] No Members tab (hidden for personal)
- [ ] Only Profile and Billing options available

---

### **12. Color Consistency**

**Check Throughout:**
- [ ] All primary actions use #0000FF (Create Team, Invite Member, Send Invite)
- [ ] Hover states use #0000CC (darker blue)
- [ ] Selected items have blue backgrounds
- [ ] Role badges use appropriate colors:
  - [ ] Owner: Gold/Orange (#f59e0b)
  - [ ] Admin: Blue (#0000FF)
  - [ ] Member: Grey (#6b6b6b)
  - [ ] Viewer: Grey (#6b6b6b)
- [ ] Pending status: Orange (#f59e0b)
- [ ] Active status: Green (#10b981)
- [ ] Remove/Delete: Red (#dc2626)

---

### **13. Accessibility & UX**

**Test Interactions:**
- [ ] All modals can be closed by:
  - [ ] Clicking X button
  - [ ] Clicking Cancel button
  - [ ] Clicking outside (backdrop for profile dropdown only)
- [ ] All buttons have hover states
- [ ] All form fields have focus states (blue ring)
- [ ] Disabled buttons have reduced opacity
- [ ] Dropdowns close when clicking outside
- [ ] Icons are meaningful and match their function

**Test Responsive Behavior:**
- [ ] Modals center on screen
- [ ] Team Members table is readable
- [ ] Long team names don't break layout
- [ ] Long email addresses don't break layout

---

## 🐛 Common Issues to Watch For

1. **Profile dropdown not showing all teams:**
   - Check if dropdown was updated with the fix from `/dropdown-fix.txt`

2. **Members tab not appearing:**
   - Only shows for teams, not personal workspace
   - Check if currentTeam.type === 'team'

3. **Can't invite members:**
   - Make sure you're on a team workspace (not personal)
   - Check Settings was passed the correct props

4. **TypeScript errors:**
   - Ensure all interfaces match between Dashboard, Settings, and TeamMembers

5. **State not persisting:**
   - This is expected - it's frontend-only mock data
   - Refreshing the page will reset everything

---

## ✨ Success Criteria

All tests passed! You should be able to:
- ✅ Create multiple teams
- ✅ Switch between teams seamlessly
- ✅ See correct team info in all locations
- ✅ Invite team members with different roles
- ✅ Manage members (change roles, remove)
- ✅ See appropriate UI for each role
- ✅ Have consistent blue color scheme
- ✅ Navigate between Profile and Members in Settings

---

## 📸 Screenshots to Verify

If everything works, you should see:
1. **Profile dropdown with multiple teams** (each showing team name and type)
2. **Create Team modal** (clean, centered, blue accents)
3. **Settings with Members tab** (only on team workspaces)
4. **Team Members page** (professional table with role badges)
5. **Invite Member modal** (email + role selection)
6. **Member action menu** (change role, remove options)

---

**Final Note:** All functionality is frontend-only with mock data. No actual invitations are sent, and data doesn't persist across page refreshes. To add real backend functionality, you'd need to integrate with Supabase or another database.
