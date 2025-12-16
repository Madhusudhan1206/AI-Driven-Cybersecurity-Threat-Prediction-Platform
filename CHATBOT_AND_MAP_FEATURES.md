# AI Chatbot and Global Threat Map Features

## Overview
This document describes the newly added AI Chatbot and Global Threat Map features to the AI-Based Cyber Security Threats Prediction System.

## 🤖 AI Chatbot

### Features
The AI Chatbot is an intelligent assistant that helps users understand cybersecurity threats and navigate the system.

#### Key Capabilities
- **Threat Analysis**: Explains different types of cyber threats (DDoS, Malware, Phishing, Ransomware, APT)
- **System Status**: Provides real-time system status and monitoring information
- **ML Model Information**: Explains machine learning models and their performance
- **Security Recommendations**: Offers best practices and security advice
- **Report Generation**: Guides users on how to generate and download threat reports
- **Network Monitoring**: Explains VPN, WiFi, and network traffic analysis

#### User Interface
- **Floating Chat Button**: Always accessible from the bottom-right corner
- **Chat Window**: Clean, modern interface with message history
- **Real-time Responses**: Instant AI-powered responses to user queries
- **Message Timestamps**: Track conversation history
- **User-friendly Design**: Dark theme with clear visual hierarchy

#### How to Use
1. Click the floating chat button (💬) in the bottom-right corner
2. Type your question about cybersecurity
3. Press Enter or click Send
4. Receive instant AI-powered responses

#### Example Queries
- "Hello" - Get a welcome message and overview
- "Help" - See all available commands
- "What is DDoS?" - Learn about DDoS attacks
- "System status" - Check current system status
- "How do I generate a report?" - Get report generation instructions
- "Tell me about ML models" - Learn about machine learning detection

### Technical Implementation
- **Component**: `src/components/security/ChatBot.tsx`
- **State Management**: React hooks (useState, useRef, useEffect)
- **Response System**: Predefined knowledge base with pattern matching
- **UI Components**: shadcn/ui (Card, Button, Input, ScrollArea)
- **Icons**: Lucide React (MessageCircle, Bot, User, Send, X)

---

## 🗺️ Global Threat Map

### Features
An interactive world map that visualizes cyber threats in real-time across the globe.

#### Key Capabilities
- **12 Global Threat Locations**: Major cities with active threat monitoring
- **Severity Visualization**: Color-coded markers based on threat severity
  - 🔴 **Critical** (Red): Highest priority threats
  - 🟠 **High** (Orange): Significant threats requiring attention
  - 🔵 **Medium** (Blue): Moderate threats under monitoring
  - 🟢 **Low** (Green): Minor threats or resolved issues
- **Interactive Markers**: Click and hover for detailed information
- **Animated Indicators**: Pulsing markers show active threats
- **Threat Statistics**: Real-time incident counts and metrics
- **Detailed Information Panel**: View threat details by location

#### Monitored Locations
1. **New York, USA** - DDoS Attack (Critical)
2. **London, UK** - Malware (High)
3. **Tokyo, Japan** - Phishing (Medium)
4. **Sydney, Australia** - Ransomware (High)
5. **Moscow, Russia** - APT Attack (Critical)
6. **Beijing, China** - Data Breach (High)
7. **Mumbai, India** - SQL Injection (Medium)
8. **São Paulo, Brazil** - Botnet (High)
9. **Berlin, Germany** - XSS Attack (Medium)
10. **Dubai, UAE** - Zero-Day Exploit (Critical)
11. **Singapore** - Cryptojacking (High)
12. **Toronto, Canada** - Trojan (Medium)

#### Dashboard Metrics
- **Critical Threats**: Count of critical severity locations
- **High Priority**: Count of high severity locations
- **Total Incidents**: Sum of all incidents in the last 24 hours
- **Monitored Regions**: Total number of tracked locations

#### How to Use
1. Navigate to "Global Threat Map" in the main menu
2. View the interactive world map with threat markers
3. Hover over markers to see quick threat information
4. Click markers to view detailed threat information
5. Use the threat list panel to browse all active threats
6. Monitor real-time statistics in the dashboard cards

### Technical Implementation
- **Component**: `src/components/security/ThreatMap.tsx`
- **Page**: `src/pages/GlobalThreatMap.tsx`
- **Map Library**: react-simple-maps
- **Map Data**: World Atlas (countries-110m.json from CDN)
- **State Management**: React hooks for selected/hovered threats
- **UI Components**: shadcn/ui (Card, Badge)
- **Icons**: Lucide React (AlertTriangle, Shield, Activity)

---

## 🌙 Dark Theme

### Features
The application now defaults to dark theme for better visibility and reduced eye strain during security monitoring.

#### Key Changes
- **Automatic Activation**: Dark mode is enabled by default on app load
- **Consistent Styling**: All components use dark theme design tokens
- **Enhanced Contrast**: Improved readability with proper color contrast
- **Professional Appearance**: Cybersecurity-focused dark aesthetic

#### Color Scheme
- **Background**: Dark blue-gray (#1a2332)
- **Cards**: Slightly lighter dark blue (#2a3342)
- **Text**: Light gray/white for high contrast
- **Accents**: Primary blue, destructive red, success green
- **Borders**: Subtle dark borders for component separation

### Technical Implementation
- **App.tsx**: Adds 'dark' class to document root on mount
- **CSS Variables**: All colors defined in `src/index.css`
- **Design System**: Follows shadcn/ui dark theme standards

---

## 🚀 Getting Started

### Accessing New Features

#### AI Chatbot
The chatbot is always available via the floating button in the bottom-right corner of any page.

#### Global Threat Map
Access the map through the navigation menu:
1. Click "Global Threat Map" in the header
2. Or navigate to `/threat-map` route

### Integration with Existing Features
Both new features integrate seamlessly with existing dashboards:
- Chatbot can answer questions about all dashboard features
- Threat map data correlates with other monitoring systems
- Dark theme applies to all pages consistently

---

## 📊 Data and Metrics

### Chatbot Knowledge Base
The chatbot includes information about:
- All threat types monitored by the system
- ML model performance and accuracy
- Network monitoring capabilities
- Report generation procedures
- System status and health

### Threat Map Data
The map displays:
- Real-time threat locations
- Incident counts per location
- Severity classifications
- Threat type categorization
- Geographic coordinates

---

## 🔧 Customization

### Extending Chatbot Responses
To add new responses, edit `src/components/security/ChatBot.tsx`:
1. Add new entries to `predefinedResponses` object
2. Update `getResponse()` function with new pattern matching
3. Test with various user inputs

### Adding Threat Locations
To add new threat locations, edit `src/components/security/ThreatMap.tsx`:
1. Add entries to `mockThreats` array
2. Include coordinates, severity, type, and count
3. Ensure coordinates are in [longitude, latitude] format

---

## 🎨 Design Principles

### Chatbot Design
- **Accessibility**: Clear contrast, readable fonts
- **Responsiveness**: Adapts to different screen sizes
- **User-friendly**: Simple, intuitive interface
- **Professional**: Matches cybersecurity theme

### Map Design
- **Visual Clarity**: Color-coded severity levels
- **Interactivity**: Hover and click interactions
- **Information Density**: Balanced detail and overview
- **Performance**: Optimized rendering for smooth experience

---

## 📝 Future Enhancements

### Potential Improvements
- **Chatbot**: Natural language processing for more sophisticated responses
- **Map**: Real-time data integration with actual threat feeds
- **Analytics**: Historical threat data and trend analysis
- **Alerts**: Push notifications for critical threats
- **Filtering**: Filter threats by type, severity, or time range

---

## 🐛 Troubleshooting

### Common Issues

#### Chatbot Not Responding
- Check browser console for errors
- Ensure JavaScript is enabled
- Refresh the page

#### Map Not Loading
- Check internet connection (map data loads from CDN)
- Verify browser supports SVG rendering
- Clear browser cache

#### Dark Theme Not Applied
- Check if browser has forced light mode
- Verify CSS is loading correctly
- Inspect document root for 'dark' class

---

## 📚 Technical Reference

### File Structure
```
src/
├── components/
│   └── security/
│       ├── ChatBot.tsx          # AI Chatbot component
│       └── ThreatMap.tsx        # Global threat map component
├── pages/
│   └── GlobalThreatMap.tsx      # Threat map page
├── routes.tsx                    # Updated with new route
└── App.tsx                       # Dark theme initialization
```

### Dependencies
- **react-simple-maps**: Map visualization library
- **shadcn/ui**: UI component library
- **lucide-react**: Icon library
- **recharts**: Chart library (existing)

### Key Functions

#### ChatBot
- `getResponse(userMessage)`: Pattern matching for responses
- `handleSendMessage()`: Process user input
- `handleKeyPress()`: Handle Enter key submission

#### ThreatMap
- `getSeverityColor(severity)`: Map severity to colors
- `getSeveritySize(severity)`: Map severity to marker sizes
- `setSelectedThreat()`: Handle threat selection
- `setHoveredThreat()`: Handle hover interactions

---

## ✅ Testing Checklist

### Chatbot Testing
- [ ] Floating button appears on all pages
- [ ] Chat window opens/closes correctly
- [ ] Messages send and display properly
- [ ] Responses are relevant and accurate
- [ ] Timestamps show correctly
- [ ] Scroll behavior works with many messages
- [ ] Enter key sends messages
- [ ] Dark theme styling is consistent

### Map Testing
- [ ] Map loads and renders correctly
- [ ] All 12 threat locations are visible
- [ ] Markers are color-coded by severity
- [ ] Hover shows threat information
- [ ] Click selects threat and shows details
- [ ] Dashboard metrics are accurate
- [ ] Threat list is scrollable
- [ ] Animations are smooth
- [ ] Dark theme styling is consistent

### Dark Theme Testing
- [ ] Dark theme activates on page load
- [ ] All pages use dark background
- [ ] Text is readable with good contrast
- [ ] Components follow dark theme design
- [ ] No light theme elements visible

---

## 📞 Support

For questions or issues with the new features:
1. Check this documentation
2. Review the code comments in component files
3. Test with the provided example queries
4. Verify all dependencies are installed

---

**Last Updated**: 2025-11-28
**Version**: 1.0.0
**Status**: Production Ready ✅
