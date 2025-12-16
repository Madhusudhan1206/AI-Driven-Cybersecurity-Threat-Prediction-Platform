# VS Code Setup Guide for CyberShield AI

## Quick Start

### 1. Open Project in VS Code
```bash
# Navigate to project directory
cd /workspace/app-7vfk0ympmqdd

# Open in VS Code
code .
```

### 2. Install Dependencies
```bash
# Using npm
npm install

# Or using pnpm (recommended)
pnpm install
```

### 3. Start Development Server
```bash
# Start the dev server
npm run dev

# The application will be available at http://localhost:5173
```

## Available Scripts

```bash
# Development
npm run dev          # Start development server with hot reload

# Building
npm run build        # Create production build
npm run preview      # Preview production build locally

# Code Quality
npm run lint         # Run ESLint to check code quality
npm run type-check   # Run TypeScript type checking
```

## Recommended VS Code Extensions

Install these extensions for the best development experience:

1. **ESLint** (`dbaeumer.vscode-eslint`)
   - Provides real-time linting feedback
   - Auto-fixes issues on save

2. **Prettier** (`esbenp.prettier-vscode`)
   - Code formatting
   - Consistent code style

3. **TypeScript Vue Plugin (Volar)** (`Vue.volar`)
   - Enhanced TypeScript support
   - Better IntelliSense

4. **Tailwind CSS IntelliSense** (`bradlc.vscode-tailwindcss`)
   - Autocomplete for Tailwind classes
   - CSS preview on hover

5. **Path Intellisense** (`christian-kohler.path-intellisense`)
   - Autocomplete for file paths
   - Helpful for imports

## VS Code Settings

Add these to your `.vscode/settings.json`:

```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "typescript.tsdk": "node_modules/typescript/lib",
  "typescript.enablePromptUseWorkspaceTsdk": true,
  "files.associations": {
    "*.css": "tailwindcss"
  },
  "tailwindCSS.experimental.classRegex": [
    ["cva\\(([^)]*)\\)", "[\"'`]([^\"'`]*).*?[\"'`]"],
    ["cn\\(([^)]*)\\)", "(?:'|\"|`)([^']*)(?:'|\"|`)"]
  ]
}
```

## Project Structure Overview

```
app-7vfk0ympmqdd/
├── src/
│   ├── components/       # Reusable UI components
│   │   ├── common/      # Shared components (Header, Footer)
│   │   ├── security/    # Security-specific components
│   │   └── ui/          # shadcn/ui components
│   ├── pages/           # Page components (dashboards)
│   ├── lib/             # Utility functions and helpers
│   ├── types/           # TypeScript type definitions
│   ├── App.tsx          # Main application component
│   ├── main.tsx         # Application entry point
│   └── index.css        # Global styles
├── public/              # Static assets
├── index.html           # HTML template
├── package.json         # Dependencies and scripts
├── tsconfig.json        # TypeScript configuration
├── vite.config.ts       # Vite configuration
└── tailwind.config.mjs  # Tailwind CSS configuration
```

## Common Development Tasks

### Adding a New Component
```typescript
// src/components/security/MyComponent.tsx
import { Card } from '@/components/ui/card';

export function MyComponent() {
  return (
    <Card>
      {/* Your component code */}
    </Card>
  );
}
```

### Adding a New Page
```typescript
// src/pages/MyPage.tsx
export default function MyPage() {
  return (
    <div className="min-h-screen bg-gradient-background p-6">
      <h1 className="text-3xl font-bold gradient-text">My Page</h1>
      {/* Page content */}
    </div>
  );
}

// Then add to src/routes.tsx
```

### Using Charts
```typescript
import { ThreatLineChart } from '@/components/security/ThreatLineChart';

// In your component
<ThreatLineChart 
  data={yourData} 
  title="Your Chart Title" 
/>
```

### Adding Toast Notifications
```typescript
import { toast } from 'sonner';

// Success notification
toast.success('Operation completed successfully');

// Error notification
toast.error('Something went wrong');

// Info notification
toast.info('Processing your request...');
```

## Debugging in VS Code

### 1. Create Launch Configuration
Create `.vscode/launch.json`:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "chrome",
      "request": "launch",
      "name": "Launch Chrome",
      "url": "http://localhost:5173",
      "webRoot": "${workspaceFolder}/src",
      "sourceMaps": true
    }
  ]
}
```

### 2. Set Breakpoints
- Click on the left margin of any line to set a breakpoint
- Press F5 to start debugging
- Use the debug toolbar to step through code

## Troubleshooting

### Port Already in Use
```bash
# Kill process on port 5173
npx kill-port 5173

# Or use a different port
npm run dev -- --port 3000
```

### Module Not Found Errors
```bash
# Clear node_modules and reinstall
rm -rf node_modules package-lock.json
npm install
```

### TypeScript Errors
```bash
# Run type check to see all errors
npm run type-check

# Restart TypeScript server in VS Code
# Press Ctrl+Shift+P (Cmd+Shift+P on Mac)
# Type: "TypeScript: Restart TS Server"
```

### Build Errors
```bash
# Clear Vite cache
rm -rf node_modules/.vite

# Rebuild
npm run build
```

## Git Workflow

```bash
# Check status
git status

# Stage changes
git add .

# Commit changes
git commit -m "Your commit message"

# View commit history
git log --oneline

# Create a new branch
git checkout -b feature/your-feature-name

# Switch branches
git checkout main
```

## Performance Tips

1. **Use React DevTools**
   - Install React Developer Tools extension for Chrome/Firefox
   - Inspect component hierarchy and props
   - Profile component performance

2. **Monitor Bundle Size**
   ```bash
   npm run build
   # Check dist/ folder size
   ```

3. **Lazy Load Components**
   ```typescript
   const MyComponent = lazy(() => import('./MyComponent'));
   ```

## Additional Resources

- [React Documentation](https://react.dev/)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
- [Tailwind CSS Docs](https://tailwindcss.com/docs)
- [shadcn/ui Components](https://ui.shadcn.com/)
- [Recharts Documentation](https://recharts.org/)
- [Vite Guide](https://vitejs.dev/guide/)

## Support

For issues or questions:
1. Check the IMPLEMENTATION_SUMMARY.md file
2. Review error messages in the terminal
3. Check browser console for runtime errors
4. Verify all dependencies are installed correctly

---

**Happy Coding! 🚀**
