# 🧪 Testing Guide - AI Cybersecurity System v3.0

## Quick Start Testing in VS Code

### Prerequisites
```bash
Node.js >= 20
npm >= 10
```

### Step 1: Install Dependencies
```bash
cd /workspace/app-7vfk0ympmqdd
npm install
```

### Step 2: Start Development Server
```bash
npm run dev -- --host 127.0.0.1
```

The application will start at: `http://127.0.0.1:5173`

---

## 🎯 Feature Testing Checklist

### ✅ 1. Enhanced AI Chatbot Testing

**Location**: Bottom-right corner (pulsing button with sparkles)

**Test Steps:**
1. **Open Chatbot**
   - Click the pulsing blue button at bottom-right
   - ✅ Chatbot window should open with welcome message
   - ✅ Should see "Advanced" badge and "Online" status

2. **Test Typing**
   - Type "hello" in the input field
   - Press Enter or click Send button
   - ✅ Your message should appear on the right (blue background)
   - ✅ Bot should show typing indicator (3 animated dots)
   - ✅ Bot response should appear on the left after 1-2 seconds

3. **Test Suggested Questions**
   - Click any of the 4 suggested action buttons:
     - "Analyze current threats"
     - "Show system metrics"
     - "ML model performance"
     - "Critical alerts"
   - ✅ Each button should send the question automatically
   - ✅ Bot should respond with relevant information

4. **Test Different Queries**
   Try these commands:
   - "analyze threats" → Should show threat analysis report
   - "show metrics" → Should show system performance
   - "critical alerts" → Should show urgent alerts (red background)
   - "help" → Should show available commands
   - "ddos" → Should explain DDoS attacks
   - "malware" → Should explain malware threats
   - "ml performance" → Should show ML model stats

5. **Test Export Feature**
   - Click the Download icon (top-right of chatbot)
   - ✅ Should download a .txt file with chat history
   - ✅ Should show success toast notification

6. **Test Scrolling**
   - Send multiple messages (10+)
   - ✅ Chat area should scroll automatically
   - ✅ Should be able to scroll up to see old messages
   - ✅ New messages should auto-scroll to bottom

7. **Test Close/Reopen**
   - Click X button to close chatbot
   - Click pulsing button to reopen
   - ✅ Chat history should be preserved

**Expected Results:**
- ✅ All messages display correctly
- ✅ Typing indicator works
- ✅ Suggested questions work
- ✅ Export downloads file
- ✅ Scrolling works smoothly
- ✅ No console errors

---

### ✅ 2. Particle Background Testing

**Location**: Visible on all pages

**Test Steps:**
1. **Visual Check**
   - Look at the background of any page
   - ✅ Should see ~80 small blue particles moving
   - ✅ Particles should connect with thin lines when close
   - ✅ Animation should be smooth (60fps)

2. **Performance Check**
   - Open browser DevTools (F12)
   - Go to Performance tab
   - ✅ CPU usage should be < 5%
   - ✅ No lag or stuttering

3. **Interaction Check**
   - Particles should NOT interfere with clicking buttons
   - ✅ All UI elements should be clickable
   - ✅ Particles should be behind content (z-index)

**Expected Results:**
- ✅ Particles animate smoothly
- ✅ Connections draw between nearby particles
- ✅ No performance issues
- ✅ Doesn't block UI interactions

---

### ✅ 3. Threat Feed Ticker Testing

**Location**: Below the header on all pages

**Test Steps:**
1. **Visual Check**
   - Look at the scrolling bar below the header
   - ✅ Should see threats scrolling from right to left
   - ✅ Each threat has: icon, type, location, severity badge

2. **Pause on Hover**
   - Hover mouse over the ticker
   - ✅ Scrolling should pause
   - Move mouse away
   - ✅ Scrolling should resume

3. **Auto-Update**
   - Watch the ticker for 5-10 seconds
   - ✅ New threats should appear periodically
   - ✅ Severity colors should vary (red, orange, blue, green)

4. **Severity Colors**
   - Critical: Red badge
   - High: Orange badge
   - Medium: Blue badge
   - Low: Green badge
   - ✅ All colors should be visible

**Expected Results:**
- ✅ Smooth scrolling animation
- ✅ Pause on hover works
- ✅ Auto-updates with new threats
- ✅ Color-coded severity levels

---

### ✅ 4. Command Palette Testing

**Location**: Accessible from anywhere

**Test Steps:**
1. **Open Command Palette**
   - Press `Cmd+K` (Mac) or `Ctrl+K` (Windows/Linux)
   - ✅ Modal should open with command list

2. **Test Navigation Commands**
   - Type "home" → Should show "Go to Overview"
   - Press Enter
   - ✅ Should navigate to Home page
   
   Try all navigation commands:
   - "static" → Static Data Dashboard
   - "streaming" → Streaming Data Dashboard
   - "network" → Network Dashboard
   - "ml" → ML Dashboard
   - "reports" → Threat Reports
   - "map" → Global Threat Map

3. **Test Search**
   - Open command palette (Cmd+K)
   - Type "threat"
   - ✅ Should filter to show only threat-related commands

4. **Test Keyboard Navigation**
   - Open command palette
   - Use ↑↓ arrow keys
   - ✅ Should highlight different commands
   - Press Enter
   - ✅ Should execute highlighted command

5. **Test Close**
   - Press ESC
   - ✅ Should close command palette
   - Click outside modal
   - ✅ Should also close

**Expected Results:**
- ✅ Opens with Cmd+K / Ctrl+K
- ✅ All navigation commands work
- ✅ Search filters correctly
- ✅ Keyboard navigation works
- ✅ ESC closes palette

---

### ✅ 5. Enhanced Global Threat Map Testing

**Location**: Navigate to "Global Threat Map" page

**Test Steps:**
1. **Visual Check**
   - ✅ Should see world map with 30+ location markers
   - ✅ Markers should pulse with different colors
   - ✅ Should see 5 statistics cards at top

2. **Test Filtering**
   - Click the "Filter by Severity" dropdown
   - Select "Critical"
   - ✅ Should show only red markers
   - Select "All"
   - ✅ Should show all markers again

3. **Test Connections**
   - Click "Toggle Connections" button
   - ✅ Should show red dashed lines between critical threats
   - Click again
   - ✅ Lines should disappear

4. **Test Hover**
   - Hover over any marker
   - ✅ Marker should scale up slightly
   - ✅ Cursor should change to pointer

5. **Test Click**
   - Click any marker
   - ✅ Should show threat details in a card
   - ✅ Card should show: location, type, severity, incidents, trend

6. **Test Statistics Cards**
   - Look at the 5 cards at top
   - ✅ Should show: Total Threats, Critical, High Priority, Total Incidents, Active Locations
   - ✅ Numbers should update when filtering

7. **Test Trend Indicators**
   - Look at threat details
   - ✅ Should see ↑ (increasing), ↓ (decreasing), or → (stable) arrows
   - ✅ Arrows should be color-coded (red/green/gray)

**Expected Results:**
- ✅ Map displays 30+ locations
- ✅ Filtering works correctly
- ✅ Connections toggle works
- ✅ Hover effects work
- ✅ Click shows details
- ✅ Statistics update correctly

---

### ✅ 6. Dashboard Testing

**Test Each Dashboard:**

#### Home / Overview Dashboard
1. Navigate to Home
2. ✅ Should see 8 metric cards at top
3. ✅ Should see 3 charts (Line, Pie, Area)
4. ✅ Should see recent threats list
5. ✅ Charts should animate on load
6. ✅ Data should auto-update every 5 seconds

#### Static Data Dashboard
1. Navigate to Static Data Dashboard
2. ✅ Should see upload area
3. ✅ Should see data analysis section
4. ✅ Should see charts and metrics

#### Streaming Data Dashboard
1. Navigate to Streaming Data Dashboard
2. ✅ Should see real-time metrics
3. ✅ Should see live charts updating
4. ✅ Should see streaming status indicator

#### Network Dashboard
1. Navigate to Network Dashboard
2. ✅ Should see VPN/WiFi metrics
3. ✅ Should see network traffic charts
4. ✅ Should see connection status

#### ML Dashboard
1. Navigate to ML Dashboard
2. ✅ Should see model performance metrics
3. ✅ Should see accuracy charts
4. ✅ Should see training status

#### Threat Reports
1. Navigate to Threat Reports
2. ✅ Should see list of reports
3. ✅ Should be able to download reports
4. ✅ Should see report details

---

## 🐛 Troubleshooting

### Chatbot Not Responding
**Problem**: Chatbot doesn't respond to messages

**Solutions**:
1. Check browser console (F12) for errors
2. Verify input field is not disabled
3. Try clicking suggested questions instead
4. Refresh the page (F5)
5. Clear browser cache

**Test**: Type "hello" and press Enter
- ✅ Should see typing indicator
- ✅ Should get response within 2 seconds

---

### Particle Background Not Showing
**Problem**: No particles visible

**Solutions**:
1. Check if browser supports Canvas API
2. Verify z-index layering
3. Check opacity setting (default 0.3)
4. Try different browser

**Test**: Look at background
- ✅ Should see moving blue dots
- ✅ Should see connecting lines

---

### Command Palette Not Opening
**Problem**: Cmd+K / Ctrl+K doesn't work

**Solutions**:
1. Verify keyboard shortcut (Mac: Cmd+K, Windows: Ctrl+K)
2. Check for conflicting browser extensions
3. Try clicking a button first, then press Cmd+K
4. Ensure JavaScript is enabled

**Test**: Press Cmd+K (or Ctrl+K)
- ✅ Modal should open immediately
- ✅ Should show list of commands

---

### Threat Feed Not Scrolling
**Problem**: Ticker not moving

**Solutions**:
1. Check CSS animations are enabled
2. Verify browser supports animations
3. Try hovering to pause/resume
4. Refresh page

**Test**: Watch ticker for 5 seconds
- ✅ Should scroll continuously
- ✅ Should pause on hover

---

### Map Not Loading
**Problem**: Global Threat Map is blank

**Solutions**:
1. Wait 2-3 seconds for map to load
2. Check browser console for errors
3. Verify react-simple-maps is installed
4. Refresh page

**Test**: Navigate to Global Threat Map
- ✅ Should see world map within 2 seconds
- ✅ Should see markers on map

---

## 🔍 Console Testing

### Check for Errors
1. Open browser DevTools (F12)
2. Go to Console tab
3. ✅ Should see no red errors
4. ✅ May see blue info messages (OK)

### Check Network
1. Go to Network tab
2. Refresh page
3. ✅ All resources should load (status 200)
4. ✅ No failed requests (red)

### Check Performance
1. Go to Performance tab
2. Record for 5 seconds
3. ✅ FPS should be ~60
4. ✅ CPU usage should be < 10%

---

## ✅ Complete Testing Checklist

### Core Features
- [ ] Chatbot opens and responds
- [ ] Chatbot suggested questions work
- [ ] Chatbot export works
- [ ] Chatbot scrolling works
- [ ] Particle background animates
- [ ] Threat feed scrolls
- [ ] Threat feed pauses on hover
- [ ] Command palette opens (Cmd+K)
- [ ] Command palette navigation works
- [ ] Global map shows 30+ locations
- [ ] Map filtering works
- [ ] Map connections toggle works

### All Pages
- [ ] Home page loads
- [ ] Static Data Dashboard loads
- [ ] Streaming Data Dashboard loads
- [ ] Network Dashboard loads
- [ ] ML Dashboard loads
- [ ] Threat Reports loads
- [ ] Global Threat Map loads

### Navigation
- [ ] Header navigation works
- [ ] All menu items clickable
- [ ] Command palette navigation works
- [ ] Back button works

### Visual
- [ ] Dark theme applied
- [ ] Colors look correct
- [ ] Animations smooth (60fps)
- [ ] No layout issues
- [ ] Responsive design works

### Performance
- [ ] Page loads < 3 seconds
- [ ] Animations smooth
- [ ] No lag or stuttering
- [ ] CPU usage < 10%
- [ ] Memory usage reasonable

---

## 🎓 Testing Tips

### Best Practices
1. **Test in Multiple Browsers**
   - Chrome (recommended)
   - Firefox
   - Safari
   - Edge

2. **Test Different Screen Sizes**
   - Desktop (1920x1080)
   - Laptop (1366x768)
   - Tablet (768x1024)
   - Mobile (375x667)

3. **Test Interactions**
   - Click all buttons
   - Hover over elements
   - Use keyboard shortcuts
   - Try edge cases

4. **Check Console**
   - Look for errors
   - Check network requests
   - Monitor performance

5. **Test Data Flow**
   - Verify data updates
   - Check real-time features
   - Test auto-refresh

---

## 📊 Expected Performance

### Load Times
- Initial page load: < 3 seconds
- Page navigation: < 500ms
- Chatbot open: < 200ms
- Command palette: < 200ms
- Map render: < 1 second

### Animation Performance
- All animations: 60fps
- Particle system: 60fps
- Threat feed: 60fps
- Chart animations: 60fps

### Resource Usage
- Memory: < 100MB
- CPU: < 10%
- Network: Minimal after initial load

---

## 🚀 Quick Test Script

Run this quick test to verify everything works:

1. **Start Application**
   ```bash
   npm run dev -- --host 127.0.0.1
   ```

2. **Open Browser**
   - Go to http://127.0.0.1:5173

3. **Quick Tests** (2 minutes)
   - ✅ See particle background
   - ✅ See threat feed scrolling
   - ✅ Press Cmd+K → Command palette opens
   - ✅ Click chatbot button → Opens
   - ✅ Type "hello" → Gets response
   - ✅ Navigate to Global Threat Map → Shows map

4. **If All Pass** ✅
   - Application is working correctly!

5. **If Any Fail** ❌
   - Check troubleshooting section
   - Check browser console for errors
   - Verify all dependencies installed

---

## 📞 Support

### Getting Help
- Check browser console (F12) for errors
- Review troubleshooting section
- Check ADVANCED_FEATURES.md for details
- Verify Node.js and npm versions

### Common Issues
1. **Port already in use**
   - Change port: `npm run dev -- --host 127.0.0.1 --port 5174`

2. **Dependencies missing**
   - Run: `npm install`

3. **Build errors**
   - Run: `npm run lint`
   - Check console output

---

## ✅ Success Criteria

Your application is working correctly if:

- ✅ All pages load without errors
- ✅ Chatbot responds to messages
- ✅ Particle background animates
- ✅ Threat feed scrolls
- ✅ Command palette opens
- ✅ Global map displays
- ✅ All navigation works
- ✅ No console errors
- ✅ Smooth 60fps animations
- ✅ All features functional

---

**Version**: 3.0.0  
**Status**: Production Ready  
**Last Updated**: 2025-11-28  

**Happy Testing!** 🎉
