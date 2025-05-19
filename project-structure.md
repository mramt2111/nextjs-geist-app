# Project Structure for Windows 11

```
indian-stock-app/
├── .env.local                    # API keys and environment variables
├── package.json                  # Project dependencies and scripts
├── tsconfig.json                 # TypeScript configuration
├── next.config.js               # Next.js configuration
├── README.md                    # Project documentation
│
├── src/
│   ├── app/
│   │   ├── layout.tsx          # Root layout with metadata
│   │   ├── dashboard/
│   │   │   └── page.tsx        # Main dashboard page
│   │   └── api/
│   │       ├── stocks/
│   │       │   └── recommendations/
│   │       │       └── route.ts # Stock recommendations API
│   │       ├── mutual-funds/
│   │       │   └── recommendations/
│   │       │       └── route.ts # Mutual fund recommendations API
│   │       └── news/
│   │           └── route.ts     # News API
│   │
│   ├── components/
│   │   ├── NewsFeed.tsx        # News feed component
│   │   └── ui/
│   │       ├── card.tsx        # Card component
│   │       ├── alert.tsx       # Alert component
│   │       └── badge.tsx       # Badge component
│   │
│   └── lib/
│       └── api.ts              # API helper functions
```

## Essential Files Content

1. `.env.local`:
```
ALPHA_VANTAGE_API_KEY=EVVLZCQ0N5YHUNLY
NEWS_API_KEY=cb506140a923426f898380a915c0d200
```

2. `package.json`:
```json
{
  "name": "indian-stock-app",
  "version": "0.1.0",
  "private": true,
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start"
  },
  "dependencies": {
    "next": "^13.4.0",
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "typescript": "^5.0.0",
    "@types/node": "^20.0.0",
    "@types/react": "^18.2.0",
    "@types/react-dom": "^18.2.0",
    "tailwindcss": "^3.3.0",
    "postcss": "^8.4.0",
    "autoprefixer": "^10.4.0"
  }
}
```

3. `tsconfig.json`:
```json
{
  "compilerOptions": {
    "target": "es5",
    "lib": ["dom", "dom.iterable", "esnext"],
    "allowJs": true,
    "skipLibCheck": true,
    "strict": true,
    "forceConsistentCasingInFileNames": true,
    "noEmit": true,
    "esModuleInterop": true,
    "module": "esnext",
    "moduleResolution": "node",
    "resolveJsonModule": true,
    "isolatedModules": true,
    "jsx": "preserve",
    "incremental": true,
    "plugins": [
      {
        "name": "next"
      }
    ],
    "paths": {
      "@/*": ["./src/*"]
    }
  },
  "include": ["next-env.d.ts", "**/*.ts", "**/*.tsx", ".next/types/**/*.ts"],
  "exclude": ["node_modules"]
}
```

4. `next.config.js`:
```javascript
/** @type {import('next').NextConfig} */
const nextConfig = {
  reactStrictMode: true,
  swcMinify: true
}

module.exports = nextConfig
```

## Installation Steps for Windows 11

1. Create project directory:
```cmd
mkdir indian-stock-app
cd indian-stock-app
```

2. Initialize project:
```cmd
npm init -y
```

3. Install dependencies:
```cmd
npm install next react react-dom typescript @types/react @types/node @types/react-dom tailwindcss postcss autoprefixer
```

4. Create the directory structure:
```cmd
mkdir src
cd src
mkdir app components lib
cd app
mkdir dashboard api
cd api
mkdir stocks mutual-funds news
cd stocks
mkdir recommendations
cd ../mutual-funds
mkdir recommendations
```

5. Copy all the source files to their respective directories as shown in the structure above.

6. Create `.env.local` in the root directory with the API keys.

7. Start the development server:
```cmd
npm run dev
```

The application will be available at `http://localhost:3000/dashboard`

## Notes
- Keep only the essential UI components in the components/ui directory
- Remove any unused components or files
- Make sure all paths in import statements use the @/ alias
- The project structure is optimized for Windows 11 development
