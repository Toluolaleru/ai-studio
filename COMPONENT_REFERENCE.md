# Team Management Components - Visual Reference

## 1. Create Team Modal (`create-team-modal.tsx`)

```
┌─────────────────────────────────────────┐
│  👥  Create New Team              ✕    │
├─────────────────────────────────────────┤
│                                         │
│  Team Name *                            │
│  ┌───────────────────────────────────┐ │
│  │ e.g., Marketing Team...           │ │
│  └───────────────────────────────────┘ │
│                                         │
│  Description (Optional)                 │
│  ┌───────────────────────────────────┐ │
│  │ What's this team for?             │ │
│  │                                   │ │
│  └───────────────────────────────────┘ │
│                                         │
│  ℹ️  You'll be able to invite team      │
│     members after creating your team.  │
│                                         │
│  ┌────────────┐  ┌─────────────────┐  │
│  │  Cancel    │  │  Create Team 🔵 │  │
│  └────────────┘  └─────────────────┘  │
└─────────────────────────────────────────┘
```

**Features:**
- Centered modal with backdrop
- Blue accent color (#0000FF)
- Required field indicator (*)
- Helpful info box
- Form validation

---

## 2. Invite Member Modal (`invite-member-modal.tsx`)

```
┌─────────────────────────────────────────┐
│  👤➕  Invite Member               ✕    │
│       Marketing Team                    │
├─────────────────────────────────────────┤
│                                         │
│  Email Address *                        │
│  ┌───────────────────────────────────┐ │
│  │ 📧 colleague@example.com          │ │
│  └───────────────────────────────────┘ │
│                                         │
│  Role                                   │
│  ┌───────────────────────────────────┐ │
│  │ ◉ Admin                           │ │
│  │   Can manage team settings        │ │
│  └───────────────────────────────────┘ │
│  ┌───────────────────────────────────┐ │
│  │ ○ Member                          │ │
│  │   Can create and edit content     │ │
│  └───────────────────────────────────┘ │
│  ┌───────────────────────────────────┐ │
│  │ ○ Viewer                          │ │
│  │   Can only view content           │ │
│  └───────────────────────────────────┘ │
│                                         │
│  ┌────────────┐  ┌─────────────────┐  │
│  │  Cancel    │  │  Send Invite 🔵 │  │
│  └────────────┘  └─────────────────┘  │
└─────────────────────────────────────────┘
```

**Features:**
- Shows team name in header
- Email validation
- Radio buttons for role selection
- Visual descriptions for each role
- Blue selected role has border

---

## 3. Team Members Page (`team-members.tsx`)

```
┌───────────────────────────────────────────────────────────────┐
│  Back  Settings                        🎫 150 left  Upgrade    │
├───────────────────────────────────────────────────────────────┤
│                                                                 │
│  👥  Team Members                     [👤➕ Invite Member]     │
│      Marketing Team • 4 members                                │
│                                                                 │
│  ┌──────────────────────────────────────────────────────────┐ │
│  │  MEMBER               ROLE          STATUS            ⋮  │ │
│  ├──────────────────────────────────────────────────────────┤ │
│  │  (J) John Doe        [👑 Owner]     ● Active             │ │
│  │  john@company.com    Gold badge                          │ │
│  │  YOU badge                                               │ │
│  ├──────────────────────────────────────────────────────────┤ │
│  │  (S) Sarah           [🛡️ Admin]     ● Active          ⋮  │ │
│  │  sarah@company.com   Blue badge                          │ │
│  ├──────────────────────────────────────────────────────────┤ │
│  │  (M) Mike            [👤 Member]    🕐 Pending        ⋮  │ │
│  │  mike@company.com    Grey badge     Orange                │ │
│  ├──────────────────────────────────────────────────────────┤ │
│  │  (L) Lisa            [👁️ Viewer]    🕐 Pending        ⋮  │ │
│  │  lisa@company.com    Grey badge     Orange                │ │
│  └──────────────────────────────────────────────────────────┘ │
│                                                                 │
│  ℹ️  About Invitations                                         │
│     Members with "Pending" status have been invited but        │
│     haven't joined yet. They'll receive an email invitation.   │
│                                                                 │
└───────────────────────────────────────────────────────────────┘

Action Menu (when clicking ⋮):
┌──────────────────────┐
│  CHANGE ROLE         │
│  ┌─────────────────┐ │
│  │ ✓ Admin         │ │
│  │   Member        │ │
│  │   Viewer        │ │
│  └─────────────────┘ │
│  ────────────────    │
│  🗑️ Remove Member   │ │ (Red text)
└──────────────────────┘
```

**Features:**
- Professional table layout
- Avatar circles with initials
- Role badges with icons:
  - 👑 Owner (gold/orange)
  - 🛡️ Admin (blue)
  - 👤 Member (grey)
  - 👁️ Viewer (grey)
- Status indicators:
  - ● Active (green dot)
  - 🕐 Pending (clock icon, orange)
- "YOU" badge for current user
- Action menu (⋮) for admins/owners
- Dropdown with role change and remove options
- Info box explaining pending status
- Invite button in header

---

## 4. Profile Dropdown (Updated in dashboard.tsx)

```
Profile Button in Top Bar:
┌────────────────────────┐
│  (J)  John Doe      ▼ │
│       john@email.com   │
└────────────────────────┘

Dropdown (when clicked):
┌─────────────────────────────────┐
│  (J)  John               ✓     │ (Blue checkmark)
│       Personal                  │
├─────────────────────────────────┤
│  (M)  Marketing Team            │
│       Team                      │
├─────────────────────────────────┤
│  (D)  Design Team               │
│       Team                      │
├─────────────────────────────────┤
│  ⊕  Create New Team             │ (Blue circle with +)
├─────────────────────────────────┤
│  ⚙️  Settings                   │
│  🚪  Logout                     │
├─────────────────────────────────┤
│  john@email.com (centered)      │
└─────────────────────────────────┘

With backdrop overlay (click outside to close)
```

**Features:**
- Lists all teams (personal + created)
- Shows team type (Personal / Team)
- Blue checkmark on current team
- Clickable team switching
- Backdrop closes dropdown
- Create New Team button
- Settings and Logout at bottom

---

## 5. Settings - Members Tab Integration

```
┌───────────────────────────────────────────────────────────────┐
│  ← Settings                             🎫 150 left  Upgrade   │
├────────┬──────────────────────────────────────────────────────┤
│        │                                                        │
│ PERSONAL SETTINGS                                              │
│  👤 Your Profile  (Blue when active)                           │
│        │                                                        │
│ WORKSPACE SETTINGS                                             │
│  (M) Marketing Team ▼                                          │
│  👥 Members  (Blue when active) ← Only visible for teams       │
│  💳 Subscription and Billing                                   │
│        │                                                        │
│        │  [Team Members Component Renders Here]                │
│        │                                                        │
└────────┴──────────────────────────────────────────────────────┘
```

**Features:**
- Sidebar navigation with tabs
- Active tab highlighted in blue (#0000FF)
- Workspace selector shows current team
- Members tab ONLY appears for team workspaces
- Hidden for personal workspace
- Clicking Members loads TeamMembers component

---

## 6. Settings - Workspace Selector

```
Left Sidebar Section:
┌──────────────────────────────────┐
│  WORKSPACE SETTINGS              │
│                                  │
│  ┌────────────────────────────┐ │
│  │ (M) Marketing Team      ▼ │ │ ← Clickable dropdown
│  └────────────────────────────┘ │
│                                  │
│  👥 Members                      │ ← Only for teams
│  💳 Subscription and Billing     │
└──────────────────────────────────┘

vs. Personal Workspace:
┌──────────────────────────────────┐
│  WORKSPACE SETTINGS              │
│                                  │
│  ┌────────────────────────────┐ │
│  │ (J) johndoe             ▼ │ │
│  └────────────────────────────┘ │
│                                  │
│  (No Members tab)                │
│  💳 Subscription and Billing     │
└──────────────────────────────────┘
```

---

## Color Scheme Reference

```
PRIMARY ACTIONS:       #0000FF (bright blue)
PRIMARY HOVER:         #0000CC (darker blue)
SELECTED/ACTIVE:       #0000FF background

ROLE COLORS:
  Owner:    #f59e0b (orange/gold)
  Admin:    #0000FF (blue)
  Member:   #6b6b6b (grey)
  Viewer:   #6b6b6b (grey)

STATUS COLORS:
  Active:   #10b981 (green)
  Pending:  #f59e0b (orange)

DESTRUCTIVE:           #dc2626 (red)
BORDERS:               #e0e0e0 (light grey)
BACKGROUNDS:
  Card:     #ffffff (white)
  Hover:    #f5f5f5 (light grey)
  Input:    #fafafa (very light grey)
  Info:     #f0f7ff (light blue)
```

---

## Icon Reference

```
👥  Users/Team
👤  User/Member
👑  Owner/Crown
🛡️  Admin/Shield
👁️  Viewer/Eye
📧  Email/Mail
✕   Close
⚙️  Settings
🚪  Logout
⋮   More actions
🗑️  Delete/Remove
✓   Checkmark/Selected
⊕   Add/Create
🎫  Tokens/Ticket
🕐  Pending/Clock
●   Active dot
ℹ️  Information
```

---

## Responsive Behavior

- **Modals:** Always centered, 400-500px max width
- **Profile Dropdown:** Fixed 280px width, right-aligned
- **Team Members Table:** Full width, scrolls horizontally if needed
- **Action Menus:** 200px width, positioned relative to trigger
- **Settings Sidebar:** Fixed 256px width

---

## State Management Flow

```
Dashboard Component State:
├── teams: Team[]
├── currentTeam: Team
├── teamMembers: { [teamId: string]: TeamMember[] }
├── showCreateTeamModal: boolean
├── showInviteMemberModal: boolean
└── showProfileDropdown: boolean

Functions:
├── handleCreateTeam(name, description)
├── handleSwitchTeam(team)
├── handleInviteMember(email, role)
├── handleRemoveMember(memberId)
└── handleUpdateMemberRole(memberId, newRole)

Props passed to Settings:
├── currentTeam
├── teamMembers
├── onInviteMember
├── onRemoveMember
└── onUpdateMemberRole

Settings passes to TeamMembers:
├── teamName
├── teamId
├── currentUserEmail
├── members
├── onInviteMember
├── onRemoveMember
└── onUpdateRole
```

---

This reference shows the visual structure and behavior of each component in the team management system. All components follow the GenFlow.ai design system with the #0000FF primary color and clean, modern interfaces.
