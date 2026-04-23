# Manual Fix Required for Profile Dropdown

## Location
**File:** `/src/app/components/dashboard.tsx`  
**Lines:** 641-709

## Problem
The profile dropdown currently shows a hardcoded "Personal" workspace entry instead of dynamically mapping through all teams.

## What to Replace

### Find This Section (Starting at line 641):

```tsx
                  {/* Profile Dropdown */}
                  {showProfileDropdown && (
                    <div className="absolute right-0 top-full mt-2 w-[280px] bg-white border border-[#e0e0e0] rounded-lg shadow-lg overflow-hidden z-50">
                      {/* Current Workspace */}
                      <div className="p-3 border-b border-[#e0e0e0] hover:bg-[#f5f5f5] cursor-pointer">
```

### Replace the Entire Dropdown Section (lines 641-709) With:

```tsx
                  {/* Profile Dropdown */}
                  {showProfileDropdown && (
                    <>
                      <div
                        className="fixed inset-0 z-40"
                        onClick={() => setShowProfileDropdown(false)}
                      />
                      <div className="absolute right-0 top-full mt-2 w-[280px] bg-white border border-[#e0e0e0] rounded-lg shadow-lg overflow-hidden z-50">
                        {/* Current Teams */}
                        <div className="max-h-[200px] overflow-y-auto border-b border-[#e0e0e0]">
                          {teams.map((team) => (
                            <button
                              key={team.id}
                              onClick={() => handleSwitchTeam(team)}
                              className="w-full p-3 hover:bg-[#f5f5f5] transition-colors text-left"
                            >
                              <div className="flex items-center justify-between">
                                <div className="flex items-center gap-3">
                                  <div className="w-10 h-10 bg-[#0000FF] rounded-full flex items-center justify-center text-white font-semibold text-[16px]">
                                    {team.name.charAt(0).toUpperCase()}
                                  </div>
                                  <div>
                                    <p className="text-[14px] text-[#1a1a1a] font-semibold">
                                      {team.name}
                                    </p>
                                    <p className="text-[12px] text-[#6b6b6b] capitalize">{team.type}</p>
                                  </div>
                                </div>
                                {currentTeam.id === team.id && (
                                  <svg className="w-5 h-5 text-[#0000FF]" fill="none" stroke="currentColor" strokeWidth="2" viewBox="0 0 24 24">
                                    <path strokeLinecap="round" strokeLinejoin="round" d="M5 13l4 4L19 7" />
                                  </svg>
                                )}
                              </div>
                            </button>
                          ))}
                        </div>

                        {/* Create New Team */}
                        <button 
                          onClick={() => {
                            setShowCreateTeamModal(true);
                            setShowProfileDropdown(false);
                          }}
                          className="w-full flex items-center gap-3 px-4 py-3 hover:bg-[#f5f5f5] transition-colors text-left"
                        >
                          <div className="w-8 h-8 rounded-full border-2 border-[#0000FF] flex items-center justify-center">
                            <Plus className="w-5 h-5 text-[#0000FF]" />
                          </div>
                          <span className="text-[14px] text-[#1a1a1a] font-medium">Create New Team</span>
                        </button>

                        <div className="border-t border-[#e0e0e0]"></div>

                        {/* Settings */}
                        <button 
                          onClick={() => {
                            setActiveMenu('settings');
                            setShowProfileDropdown(false);
                          }}
                          className="w-full flex items-center gap-3 px-4 py-3 hover:bg-[#f5f5f5] transition-colors text-left"
                        >
                          <Settings className="w-5 h-5 text-[#6b6b6b]" />
                          <span className="text-[14px] text-[#1a1a1a]">Settings</span>
                        </button>

                        {/* Logout */}
                        <button 
                          onClick={() => {
                            setShowProfileDropdown(false);
                            onLogout();
                          }}
                          className="w-full flex items-center gap-3 px-4 py-3 hover:bg-[#f5f5f5] transition-colors text-left"
                        >
                          <LogOut className="w-5 h-5 text-[#6b6b6b]" />
                          <span className="text-[14px] text-[#1a1a1a]">Logout</span>
                        </button>

                        {/* Email */}
                        <div className="px-4 py-3 bg-[#f5f5f5] border-t border-[#e0e0e0]">
                          <p className="text-[12px] text-[#6b6b6b] text-center">{userEmail}</p>
                        </div>
                      </div>
                    </>
                  )}
```

## Key Changes:

1. **Added backdrop overlay** (`<div className="fixed inset-0 z-40"...`) to close dropdown when clicking outside
2. **Replaced hardcoded workspace** with `teams.map()` to show all teams dynamically
3. **Made teams clickable** with `onClick={() => handleSwitchTeam(team)}`
4. **Shows checkmark** next to currently selected team
5. **Displays team type** (Personal / Team) instead of hardcoded "Personal"

## After Fixing:

The dropdown will now:
- Show all created teams
- Allow switching between teams
- Highlight the current team with a checkmark
- Close when clicking outside
- Work perfectly with the team management system

---

**Note:** The rest of the team management system is already complete and functional. This is the only section that needs manual updating.
